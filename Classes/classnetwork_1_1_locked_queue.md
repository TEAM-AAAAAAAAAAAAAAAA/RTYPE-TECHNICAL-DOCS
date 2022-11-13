---
title: network::LockedQueue

---

# network::LockedQueue



 [More...](#detailed-description)


`#include <LockedQueue.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[push](Classes/classnetwork_1_1_locked_queue.md#function-push)**(T value) |
| T | **[pop](Classes/classnetwork_1_1_locked_queue.md#function-pop)**() |
| bool | **[empty](Classes/classnetwork_1_1_locked_queue.md#function-empty)**() |

## Detailed Description

```cpp
template <typename T >
class network::LockedQueue;
```

## Public Functions Documentation

### function push

```cpp
inline void push(
    T value
)
```


**Parameters**: 

  * **value** value to push 


Function which pushes the value into the queue while locking it 


### function pop

```cpp
inline T pop()
```


**Return**: return the front value 

Get the top value of the queue 


### function empty

```cpp
inline bool empty()
```


**Return**: True if queue is empty 

Check if the queue is empty 


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100