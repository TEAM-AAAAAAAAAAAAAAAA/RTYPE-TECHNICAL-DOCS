---
title: src/ecs/components/client/Shootable.hpp

---

# src/ecs/components/client/Shootable.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::Shootable](Classes/structecs_1_1component_1_1_shootable.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** Shootable
*/

#pragma once

#include "SFML/Window/Keyboard.hpp"

namespace ecs::component
{
    struct Shootable {
        explicit Shootable(sf::Keyboard::Key shoot, sf::Keyboard::Key shootSecondary = sf::Keyboard::Key::Unknown)
            : Shoot(shoot), ShootSecondary(shootSecondary)
        {
        }

        sf::Keyboard::Key Shoot;

        sf::Keyboard::Key ShootSecondary;
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
