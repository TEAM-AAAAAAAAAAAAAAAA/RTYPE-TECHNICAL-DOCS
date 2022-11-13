---
title: src/ecs/components/client/Parallax.hpp

---

# src/ecs/components/client/Parallax.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::Parallax](Classes/structecs_1_1component_1_1_parallax.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** Parallax
*/

#pragma once

namespace ecs::component
{
    struct Parallax {
        int threshold;
        int position;
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
