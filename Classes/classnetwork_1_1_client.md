---
title: network::Client

---

# network::Client



 [More...](#detailed-description)


`#include <NetworkClient.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[~Client](Classes/classnetwork_1_1_client.md#function-~client)**() |
| void | **[setHost](Classes/classnetwork_1_1_client.md#function-sethost)**(const std::string & host) |
| void | **[setPort](Classes/classnetwork_1_1_client.md#function-setport)**(const std::string & port) |
| [LockedQueue](Classes/classnetwork_1_1_locked_queue.md)< [Message](Namespaces/namespacenetwork.md#typedef-message) > & | **[getOutgoingMessages](Classes/classnetwork_1_1_client.md#function-getoutgoingmessages)**() |
| [LockedQueue](Classes/classnetwork_1_1_locked_queue.md)< [Message](Namespaces/namespacenetwork.md#typedef-message) > & | **[getReceivedMessages](Classes/classnetwork_1_1_client.md#function-getreceivedmessages)**() |
| bool | **[getIsConnected](Classes/classnetwork_1_1_client.md#function-getisconnected)**() |
| void | **[setIsConnected](Classes/classnetwork_1_1_client.md#function-setisconnected)**() |
| void | **[connect](Classes/classnetwork_1_1_client.md#function-connect)**() |
| void | **[disconnect](Classes/classnetwork_1_1_client.md#function-disconnect)**() |

## Detailed Description

```cpp
class network::Client;
```


[Client](Classes/classnetwork_1_1_client.md) class is one of the big parts in the game. It represents the way for the gamer to communicate with the servers by sending and receiving some message. To understand those messages in a more specifically way, just refer to the RFC. [Client](Classes/classnetwork_1_1_client.md) is able to join a specific server by a given ip & port, communicating with it using sockets & buffers 

## Public Functions Documentation

### function ~Client

```cpp
inline ~Client()
```


Default destructor of the [Client](Classes/classnetwork_1_1_client.md) Class 


### function setHost

```cpp
static inline void setHost(
    const std::string & host
)
```


Getters & Setters of client Class 


### function setPort

```cpp
static inline void setPort(
    const std::string & port
)
```


### function getOutgoingMessages

```cpp
static inline LockedQueue< Message > & getOutgoingMessages()
```


### function getReceivedMessages

```cpp
static inline LockedQueue< Message > & getReceivedMessages()
```


### function getIsConnected

```cpp
static inline bool getIsConnected()
```


### function setIsConnected

```cpp
static inline void setIsConnected()
```


### function connect

```cpp
static inline void connect()
```


Static methods used to connect to the given server (host, port) using udp::v4 


### function disconnect

```cpp
static inline void disconnect()
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100