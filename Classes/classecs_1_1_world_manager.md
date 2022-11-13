---
title: ecs::WorldManager

---

# ecs::WorldManager






`#include <WorldManager.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[~WorldManager](Classes/classecs_1_1_world_manager.md#function-~worldmanager)**() =default |
| void | **[setWorldSwitchReady](Classes/classecs_1_1_world_manager.md#function-setworldswitchready)**(bool isReady =true) |
| [ecs::World](Classes/classecs_1_1_world.md) & | **[getWorld](Classes/classecs_1_1_world_manager.md#function-getworld)**() |
| void | **[setWaitingWorld](Classes/classecs_1_1_world_manager.md#function-setwaitingworld)**(std::function< [World](Classes/classecs_1_1_world.md)()> worldGen, bool worldSwitchReady =true) |
| void | **[setWorldSwitchReady](Classes/classecs_1_1_world_manager.md#function-setworldswitchready)**() |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| friend | **[Engine](Classes/classecs_1_1_world_manager.md#variable-engine)**  |

## Public Functions Documentation

### function ~WorldManager

```cpp
~WorldManager() =default
```


### function setWorldSwitchReady

```cpp
static inline void setWorldSwitchReady(
    bool isReady =true
)
```


### function getWorld

```cpp
static inline ecs::World & getWorld()
```


**Return**: The currently used world by the ecs 

Used to get the currentWorld currently used by the ecs 


### function setWaitingWorld

```cpp
static inline void setWaitingWorld(
    std::function< World()> worldGen,
    bool worldSwitchReady =true
)
```


**Parameters**: 

  * **world** The world you want to set to release mode 
  * **worldSwitchReady** Used to prevents of automatic world's switch 


Set the world given as parameter to release mode 


### function setWorldSwitchReady

```cpp
static inline void setWorldSwitchReady()
```


Set the world given as parameter ready to switch for another one 


## Public Attributes Documentation

### variable Engine

```cpp
friend Engine;
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100