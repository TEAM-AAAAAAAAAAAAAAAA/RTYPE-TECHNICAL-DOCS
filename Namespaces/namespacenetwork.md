---
title: network

---

# network

 [More...](#detailed-description)

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[network::Client](Classes/classnetwork_1_1_client.md)**  |
| class | **[network::LockedQueue](Classes/classnetwork_1_1_locked_queue.md)**  |
| class | **[network::Server](Classes/classnetwork_1_1_server.md)**  |

## Types

|                | Name           |
| -------------- | -------------- |
| typedef std::array< char, 16 > | **[Message](Namespaces/namespacenetwork.md#typedef-message)**  |
| typedef std::pair< [Message](Namespaces/namespacenetwork.md#typedef-message), unsigned int > | **[ClientMessage](Namespaces/namespacenetwork.md#typedef-clientmessage)**  |
| typedef std::pair< [Message](Namespaces/namespacenetwork.md#typedef-message), std::vector< unsigned int > > | **[ServerMessage](Namespaces/namespacenetwork.md#typedef-servermessage)**  |

## Detailed Description


Simple mutex-guarded queue

[Server](Classes/classnetwork_1_1_server.md) class which is used by the game server to communicate with the client 

## Types Documentation

### typedef Message

```cpp
typedef std::array<char, 16> network::Message;
```


Standard pair class that contains a string and the ID of the client that sent it 


### typedef ClientMessage

```cpp
typedef std::pair<Message, unsigned int> network::ClientMessage;
```


### typedef ServerMessage

```cpp
typedef std::pair<Message, std::vector<unsigned int> > network::ServerMessage;
```







-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100