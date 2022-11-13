---
title: src/client/GetWorld.hpp

---

# src/client/GetWorld.hpp



## Functions

|                | Name           |
| -------------- | -------------- |
| [ecs::World](Classes/classecs_1_1_world.md) | **[getGameWorld](Files/_get_world_8hpp.md#function-getgameworld)**(const std::string & port, const std::string & host) |
| [ecs::World](Classes/classecs_1_1_world.md) | **[getMenuWorld](Files/_get_world_8hpp.md#function-getmenuworld)**() |


## Functions Documentation

### function getGameWorld

```cpp
ecs::World getGameWorld(
    const std::string & port,
    const std::string & host
)
```


**Parameters**: 

  * **engine** The engine in which you want to operate 


**Return**: The world ready to be used 

This function is used to get the game part of the world. Currently registering every components to the world's registry and adding every associated systems to the world 


### function getMenuWorld

```cpp
ecs::World getMenuWorld()
```




## Source code

```cpp
/*
** EPITECH PROJECT, by hourcadettej on 11/6/22.
** rtype
** File description:
** rtype
*/

#pragma once

#include "World.hpp"

ecs::World getGameWorld(const std::string& port, const std::string &host);
ecs::World getMenuWorld();
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
