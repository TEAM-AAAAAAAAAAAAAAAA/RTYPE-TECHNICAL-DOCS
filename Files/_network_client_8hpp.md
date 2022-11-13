---
title: src/client/NetworkClient.hpp

---

# src/client/NetworkClient.hpp



## Namespaces

| Name           |
| -------------- |
| **[network](Namespaces/namespacenetwork.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[network::Client](Classes/classnetwork_1_1_client.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** NetworkClient
*/

#pragma once

#include <boost/array.hpp>
#include <boost/asio.hpp>
#include <iostream>
#include "LockedQueue.hpp"

using boost::asio::ip::udp;

namespace network
{
    class Client {
      public:
        ~Client()
        {
            getInstance()._isStillRunning = false;
            getInstance()._ioService.stop();
            getInstance()._outgoingService.join();
            getInstance()._incomingService.join();
            getInstance()._socket.close();
        }

        static inline void setHost(const std::string &host) { getInstance()._host = host; }

        static void setPort(const std::string &port) { getInstance()._port = port; }

        static inline LockedQueue<Message> &getOutgoingMessages() { return getInstance()._outgoingMessages; }

        static inline LockedQueue<Message> &getReceivedMessages() { return getInstance()._receivedMessages; }

        static inline bool getIsConnected() { return getInstance()._isConnected;}
        static inline void setIsConnected() { getInstance()._isConnected = true;}

        static inline void connect()
        {
            udp::resolver resolver(getInstance()._ioService);
            getInstance()._socket = udp::socket(getInstance()._ioService);
            udp::resolver::query query(udp::v4(), getInstance()._host, getInstance()._port);
            getInstance()._endpoint = *resolver.resolve(query);
            getInstance()._socket.open(udp::v4());
        }

        static inline void disconnect()
        {
            getInstance()._ioService.stop();
            getInstance()._socket.close();
        }

      private:
        Client()
            : _socket(_ioService), _incomingService(&Client::receiveIncoming, this),
              _outgoingService(&Client::sendOutgoing, this)
        {
        }

        boost::asio::io_service _ioService;
        udp::socket _socket;
        Message _recvBuffer{};
        udp::endpoint _endpoint;
        std::string _host;
        std::string _port;
        bool _isStillRunning = true;
        bool _isConnected = false;

        LockedQueue<Message> _outgoingMessages;

        LockedQueue<Message> _receivedMessages;

        void handleReceive(const std::error_code &error, std::size_t bytesTransferred)
        {
            if (!error) {
                try {
                    auto message = Message(_recvBuffer);
                    if (!message.empty()) {
                        network::Client::setIsConnected();
                        _receivedMessages.push(message);
                    }
                } catch (const std::exception &e) {
                    std::cerr << e.what() << '\n';
                }
            }
            startReceive();
        }

        void startReceive()
        {
            udp::endpoint senderEndpoint;

            _recvBuffer.fill(0);
            _socket.async_receive_from(boost::asio::buffer(_recvBuffer), senderEndpoint,
                [this](std::error_code ec, std::size_t bytesRecvd) { this->handleReceive(ec, bytesRecvd); });
        }

        void handleSend(Message message, const std::error_code &error, std::size_t bytesTransferred) {}

        void receiveIncoming()
        {
            while (_isStillRunning) {
                while (!_socket.is_open())
                    if (!_isStillRunning)
                        return;
                std::this_thread::sleep_for(std::chrono::milliseconds(100));
                startReceive();
                while (!_ioService.stopped()) {
                    try {
                        _ioService.run();
                    } catch (const std::exception &e) {
                        std::cerr << e.what() << '\n';
                    }
                }
            }
        }

        void sendOutgoing()
        {
            while (_isStillRunning) {
                std::this_thread::sleep_for(std::chrono::milliseconds(1000));
                while (!_socket.is_open())
                    if (!_isStillRunning)
                        return;
                while (!_ioService.stopped()) {
                    if (!_outgoingMessages.empty()) {
                        auto msg = _outgoingMessages.pop();
                        _socket.async_send_to(boost::asio::buffer(msg), _endpoint,
                            [](const boost::system::error_code &ec, std::size_t bytes) {});
                    }
                }
            }
        }

        std::thread _incomingService;
        std::thread _outgoingService;
        
        static Client &getInstance();
//        static Client getInstance();
    };
} // namespace network
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
