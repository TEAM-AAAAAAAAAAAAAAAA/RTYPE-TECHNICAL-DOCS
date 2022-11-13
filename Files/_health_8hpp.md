---
title: src/ecs/components/Health.hpp

---

# src/ecs/components/Health.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::Health](Classes/structecs_1_1component_1_1_health.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** Health
*/

#pragma once

#include "Constant.hpp"

namespace ecs::component
{
    struct Health {
        int health;
        int lastHealth = utils::constant::maxPlayerHealth;
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
