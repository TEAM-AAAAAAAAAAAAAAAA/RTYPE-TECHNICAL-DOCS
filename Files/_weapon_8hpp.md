---
title: src/ecs/components/Weapon.hpp

---

# src/ecs/components/Weapon.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::Weapon](Classes/structecs_1_1component_1_1_weapon.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** Weapon
*/

#pragma once

namespace ecs::component
{
    struct Weapon {
        Weapon(int shootDelay, int damage, int projSpeed, std::pair<unsigned char, unsigned char> projSize, bool hasSuper = false, int superDamage = 0, int superLoadingTime = 0)
            : shootDelay(shootDelay * 1000000), damage(damage), projSpeed(projSpeed), projSize(projSize), hasSuper(hasSuper), superDamage(superDamage), superLoadingTime(superLoadingTime), lastShoot(0)
        {
        }

        int shootDelay;
        int damage;
        int projSpeed;
        std::pair<unsigned char, unsigned char> projSize;
        int64_t lastShoot;
        bool hasSuper;
        int superDamage;
        int superLoadingTime;
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
