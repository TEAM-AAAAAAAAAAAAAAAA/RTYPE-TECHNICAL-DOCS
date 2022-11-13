---
title: src/ecs/components/Direction.hpp

---

# src/ecs/components/Direction.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::Direction](Classes/structecs_1_1component_1_1_direction.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** Direction
*/

#pragma once

namespace ecs::component
{
    struct Direction {
        Direction(char x, char y, bool hasMoved = false) : x(x), y(y), hasMoved(hasMoved) {}
        char x;
        char y;
        bool hasMoved;
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
