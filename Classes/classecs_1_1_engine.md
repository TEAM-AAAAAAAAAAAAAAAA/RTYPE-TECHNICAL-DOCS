---
title: ecs::Engine

---

# ecs::Engine



 [More...](#detailed-description)


`#include <Engine.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Engine](Classes/classecs_1_1_engine.md#function-engine)**() |
| void | **[run](Classes/classecs_1_1_engine.md#function-run)**() |

## Detailed Description

```cpp
class ecs::Engine;
```


The [Engine](Classes/classecs_1_1_engine.md) class manages the whole part of systems in ecs in a given world. Systems are, most of the time, short function using components to realise some actions. For example, to make an [Entity](Classes/classecs_1_1_entity.md) move, we need a component Position and a component Velocity, the system is the thing who update the position of the [Entity](Classes/classecs_1_1_entity.md) according to the Velocity component by adding velocity value to the x & y member of the component position of the [Entity](Classes/classecs_1_1_entity.md). 

## Public Functions Documentation

### function Engine

```cpp
inline explicit Engine()
```


**Parameters**: 

  * **wSizeWidth** width size of the window in pixel, 800px as default 
  * **wSizeHeight** height size of the window in pixel, 600 as default 
  * **wTitle** window's title, "r-type" as default 


Constructor of [Engine](Classes/classecs_1_1_engine.md) class, it takes care of register every component in the world's registry. It also create a player and an enemy. And finally it takes care of adding every systems related to the components in the initWorld. 


### function run

```cpp
inline void run()
```


Main loop of the current world Actually run while the window is open 


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100