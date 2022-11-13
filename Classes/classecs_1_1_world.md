---
title: ecs::World

---

# ecs::World



 [More...](#detailed-description)


`#include <World.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[World](Classes/classecs_1_1_world.md#function-world)**() |
| void | **[runSystems](Classes/classecs_1_1_world.md#function-runsystems)**() |
| void | **[addSystem](Classes/classecs_1_1_world.md#function-addsystem)**(const std::function< void([World](Classes/classecs_1_1_world.md) &)> & system) |
| void | **[pushEvent](Classes/classecs_1_1_world.md#function-pushevent)**(const [ecs::Event](Classes/classecs_1_1_event.md) event) |
| const [ecs::Event](Classes/classecs_1_1_event.md) | **[getEvent](Classes/classecs_1_1_world.md#function-getevent)**() const |
| const [ecs::Event](Classes/classecs_1_1_event.md) | **[popEvent](Classes/classecs_1_1_world.md#function-popevent)**() |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| [Registry](Classes/classecs_1_1_registry.md) | **[registry](Classes/classecs_1_1_world.md#variable-registry)**  |

## Detailed Description

```cpp
class ecs::World;
```


[World](Classes/classecs_1_1_world.md) class is used to contain all the components that are relevant to work together 

## Public Functions Documentation

### function World

```cpp
inline World()
```


Default constructor 


### function runSystems

```cpp
inline void runSystems()
```


Used to operate all the systems in the world 


### function addSystem

```cpp
inline void addSystem(
    const std::function< void(World &)> & system
)
```


**Parameters**: 

  * **system** The system you want to add in the world in a constant manner 


USed to add a new system into the world 


### function pushEvent

```cpp
inline void pushEvent(
    const ecs::Event event
)
```


**Parameters**: 

  * **event** The event you want to push in the world 


Used to add a new event into the world 


### function getEvent

```cpp
inline const ecs::Event getEvent() const
```


**Return**: The first event of the private stack if it exists, ecs::Event::EventType::Null otherwise 

Used to get the first event of the private stack _events 


### function popEvent

```cpp
inline const ecs::Event popEvent()
```


**Return**: The event you just popped out of the stack if it exists, ecs::Event::EventType::Null otherwise 

Used to pop the first event of the private stack _events 


## Public Attributes Documentation

### variable registry

```cpp
Registry registry;
```


The registry of the world, refers to the [Registry](Classes/classecs_1_1_registry.md) documentation to learn more about it 


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100