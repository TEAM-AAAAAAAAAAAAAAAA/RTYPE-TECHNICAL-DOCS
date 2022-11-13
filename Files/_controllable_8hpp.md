---
title: src/ecs/components/client/Controllable.hpp

---

# src/ecs/components/client/Controllable.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::Controllable](Classes/structecs_1_1component_1_1_controllable.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** Controllable
*/

#pragma once

#include "SFML/Window/Keyboard.hpp"

namespace ecs::component
{
    struct Controllable {
        Controllable(sf::Keyboard::Key moveUp, sf::Keyboard::Key moveLeft, sf::Keyboard::Key moveDown,
            sf::Keyboard::Key moveRight, sf::Keyboard::Key hitBox, sf::Keyboard::Key moveUpSecondary = sf::Keyboard::Unknown,
            sf::Keyboard::Key moveLeftSecondary = sf::Keyboard::Unknown,
            sf::Keyboard::Key moveDownSecondary = sf::Keyboard::Unknown,
            sf::Keyboard::Key moveRightSecondary = sf::Keyboard::Unknown)
            : MoveUp(moveUp), MoveLeft(moveLeft), MoveDown(moveDown), MoveRight(moveRight),
              HitBox(hitBox), MoveRightSecondary(moveRightSecondary), MoveUpSecondary(moveUpSecondary),
              MoveDownSecondary(moveDownSecondary), MoveLeftSecondary(moveLeftSecondary)
        {
        }

        sf::Keyboard::Key MoveUp;
        sf::Keyboard::Key MoveLeft;
        sf::Keyboard::Key MoveDown;
        sf::Keyboard::Key MoveRight;

        sf::Keyboard::Key MoveUpSecondary;
        sf::Keyboard::Key MoveLeftSecondary;
        sf::Keyboard::Key MoveDownSecondary;
        sf::Keyboard::Key MoveRightSecondary;

        sf::Keyboard::Key HitBox;
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
