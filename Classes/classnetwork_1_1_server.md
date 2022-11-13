---
title: network::Server

---

# network::Server






`#include <Server.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[~Server](Classes/classnetwork_1_1_server.md#function-~server)**() |
| bool | **[hasMessages](Classes/classnetwork_1_1_server.md#function-hasmessages)**() |
| void | **[sendToClient](Classes/classnetwork_1_1_server.md#function-sendtoclient)**(const [Message](Namespaces/namespacenetwork.md#typedef-message) & message, uint32_t clientID) |
| void | **[sendToAll](Classes/classnetwork_1_1_server.md#function-sendtoall)**(const [Message](Namespaces/namespacenetwork.md#typedef-message) & message) |
| size_t | **[getClientCount](Classes/classnetwork_1_1_server.md#function-getclientcount)**() |
| uint32_t | **[getClientIdByIndex](Classes/classnetwork_1_1_server.md#function-getclientidbyindex)**(size_t index) |
| void | **[start](Classes/classnetwork_1_1_server.md#function-start)**(unsigned short localPort) |
| [LockedQueue](Classes/classnetwork_1_1_locked_queue.md)< [ServerMessage](Namespaces/namespacenetwork.md#typedef-servermessage) > & | **[getOutgoingMessages](Classes/classnetwork_1_1_server.md#function-getoutgoingmessages)**() |
| [LockedQueue](Classes/classnetwork_1_1_locked_queue.md)< [ClientMessage](Namespaces/namespacenetwork.md#typedef-clientmessage) > & | **[GetReceivedMessages](Classes/classnetwork_1_1_server.md#function-getreceivedmessages)**() |

## Public Functions Documentation

### function ~Server

```cpp
inline ~Server()
```


Default destructor of the server Class, stopping the ioService & make all the threads join 


### function hasMessages

```cpp
static inline bool hasMessages()
```


**Return**: true if there are messages 

This function allows us to check if the server has received messages 


### function sendToClient

```cpp
static inline void sendToClient(
    const Message & message,
    uint32_t clientID
)
```


**Parameters**: 

  * **message** The message you want to send 
  * **clientID** The id of the client you want to communicate with 


Used to send a message to a client given as parameter 


### function sendToAll

```cpp
static inline void sendToAll(
    const Message & message
)
```


**Parameters**: 

  * **message** The message you want to send 


Used to send a message to every available clients 


### function getClientCount

```cpp
static inline size_t getClientCount()
```


**Return**: Amount of connected clients 

Get the amount of clients that are connected 


### function getClientIdByIndex

```cpp
static inline uint32_t getClientIdByIndex(
    size_t index
)
```


**Parameters**: 

  * **index** the index for the array 


**Return**: client ID of client n 

Get the ID of client from the clients array 


### function start

```cpp
static inline void start(
    unsigned short localPort
)
```


### function getOutgoingMessages

```cpp
static inline LockedQueue< ServerMessage > & getOutgoingMessages()
```


Getters & Setters of the [Server](Classes/classnetwork_1_1_server.md) Class 


### function GetReceivedMessages

```cpp
static inline LockedQueue< ClientMessage > & GetReceivedMessages()
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100