---
title: src/server/Server.hpp

---

# src/server/Server.hpp



## Namespaces

| Name           |
| -------------- |
| **[network](Namespaces/namespacenetwork.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[network::Server](Classes/classnetwork_1_1_server.md)**  |

## Types

|                | Name           |
| -------------- | -------------- |
| typedef std::map< uint32_t, udp::endpoint > | **[ClientList](Files/_server_8hpp.md#typedef-clientlist)**  |
| typedef ClientList::value_type | **[Client](Files/_server_8hpp.md#typedef-client)**  |

## Types Documentation

### typedef ClientList

```cpp
typedef std::map<uint32_t, udp::endpoint> ClientList;
```


### typedef Client

```cpp
typedef ClientList::value_type Client;
```





## Source code

```cpp
#pragma once
#include <array>
#include <atomic>
#include <boost/asio.hpp>
#include <boost/asio/post.hpp>
#include <boost/bind/bind.hpp>
#include <ctime>
#include <iostream>
#include <map>
#include <string>
#include <thread>
#include "LockedQueue.hpp"
#include <boost/asio/thread_pool.hpp>
#include <boost/shared_ptr.hpp>

using boost::asio::ip::udp;

typedef std::map<uint32_t, udp::endpoint> ClientList;
typedef ClientList::value_type Client;

namespace network
{
    class Server {
      public:
        ~Server()
        {
            _ioService.stop();
            _serviceThread.join();
            _outgoingService.join();
            _socket.close();
        }

        static bool hasMessages() { return !getInstance()._receivedMessages.empty(); };

        static void sendToClient(const Message &message, uint32_t clientID)
        {
            try {
                getInstance().send(message, getInstance()._clients.at(clientID));
            } catch (std::out_of_range) {
                std::cerr << "sendToClient : Unknown client ID " << clientID << std::endl;
            }
        }

        static void sendToAll(const Message &message)
        {
            for (auto client : getInstance()._clients)
                getInstance().send(message, client.second);
        }

        static size_t getClientCount() { return getInstance()._clients.size(); }

        static uint32_t getClientIdByIndex(size_t index)
        {
            auto it = getInstance()._clients.begin();
            for (int i = 0; i < index; i++)
                ++it;
            return it->first;
        }

        static inline void start(unsigned short localPort)
        {
            if (getInstance()._isRunning)
                return;
            getInstance()._socket = udp::socket(getInstance()._ioService, udp::endpoint(udp::v4(), localPort));
            getInstance()._isRunning = true;
            std::cerr << "Server started on port " << localPort << std::endl;
        }

        static LockedQueue<ServerMessage> &getOutgoingMessages() { return getInstance()._outgoingMessages; }

        static LockedQueue<ClientMessage> &GetReceivedMessages() { return getInstance()._receivedMessages; }

      private:
        LockedQueue<ServerMessage> _outgoingMessages;

        LockedQueue<ClientMessage> _receivedMessages;

        boost::asio::io_service _ioService;
        udp::endpoint _serverEndpoint;
        udp::endpoint _remoteEndpoint;
        Message _recvBuffer;
        udp::socket _socket;

        std::thread _serviceThread;
        std::thread _outgoingService;

        void startReceive()
        {
            _recvBuffer.fill(0);
            _socket.async_receive_from(boost::asio::buffer(_recvBuffer), _remoteEndpoint,
                [this](std::error_code ec, std::size_t bytesRecvd) { this->handleReceive(ec, bytesRecvd); });
        }

        void handleReceive(const std::error_code &error, std::size_t bytesTransferred)
        {
            if (!error) {
                try {
                    auto message = ClientMessage(std::array(_recvBuffer), getOrCreateClientID(_remoteEndpoint));
                    if (!message.first.empty()) {
                        _receivedMessages.push(message);
                        for (const auto &c : message.first) {}
                    }
                } catch (std::exception ex) {
                    std::cerr << "handleReceive: Error parsing incoming message:" << ex.what() << std::endl;
                } catch (...) {
                    std::cerr << "handleReceive: Unknown error while parsing incoming message" << std::endl;
                    ;
                }
            } else {
                std::cerr << "handleReceive: error: " << error.message() << " while receiving from address "
                          << _remoteEndpoint << std::endl;
            }
            startReceive();
        }

        void receiveIncoming()
        {
            while (!_isRunning) {
                std::this_thread::sleep_for(std::chrono::milliseconds(100));
            }
            startReceive();
            while (!_ioService.stopped()) {
                try {
                    _ioService.run();
                } catch (const std::exception &e) {
                    std::cerr << "Server: Network exception: " << e.what() << std::endl;
                } catch (...) {
                    std::cerr << "Server: Network exception: unknown" << std::endl;
                }
            }
            std::cerr << "Server network thread stopped" << std::endl;
        }

        int32_t getOrCreateClientID(udp::endpoint endpoint)
        {
            for (const auto &client : _clients)
                if (client.second == endpoint)
                    return client.first;

            auto id = ++_nextClientID;
            _clients.insert(Client(id, endpoint));
            return id;
        }

        void send(const Message &message, udp::endpoint endpoint)
        {
            _socket.async_send_to(
                boost::asio::buffer(message), endpoint, [](std::error_code ec, std::size_t bytesRecvd) {});
        }

        void sendOutgoing()
        {
            while (!_isRunning) {
                std::this_thread::sleep_for(std::chrono::milliseconds(100));
            }
            while (!_ioService.stopped()) {
                if (!_outgoingMessages.empty()) {
                    ServerMessage message = _outgoingMessages.pop();
                    if (message.second.empty())
                        sendToAll(message.first);
                    else
                        for (auto &client : message.second)
                            sendToClient(message.first, client);
                }
            }
        }

        ClientList _clients;
        int _nextClientID;

        bool _isRunning;

        Server()
            : _socket(_ioService), _isRunning(false), _serviceThread(&network::Server::receiveIncoming, this),
              _nextClientID(0L), _outgoingService(&network::Server::sendOutgoing, this){};

//        static Server getInstance();
        static Server &getInstance();
    };
} // namespace network
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
