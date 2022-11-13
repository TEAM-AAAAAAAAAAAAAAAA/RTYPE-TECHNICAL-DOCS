---
title: src/ecs/components/Position.hpp

---

# src/ecs/components/Position.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::Position](Classes/structecs_1_1component_1_1_position.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** Position
*/

#pragma once
#include <cstddef>
#include <array>

namespace ecs::component
{
    struct Position {
        Position(int x, int y) : x(x), y(y) {}
        int x;
        int y;
        std::array<char, 4> serialize()
        {
            std::array<char, 4> pos;
            size_t tmp = 0;

            tmp = x >> 8;
            pos[0] = tmp;
            pos[1] = x & 0xff;
            tmp = y >> 8;
            pos[2] = tmp;
            pos[3] = y & 0xff;
            return pos;
        }
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100
