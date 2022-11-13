---
title: src/ecs/components/server/Projectile.hpp

---

# src/ecs/components/server/Projectile.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::Projectile](Classes/structecs_1_1component_1_1_projectile.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** Projectile
*/

#pragma once

namespace ecs::component
{
    struct Projectile {
        Projectile(int damage) : damage(damage) {}

        int damage;
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
