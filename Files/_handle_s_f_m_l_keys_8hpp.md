---
title: src/ecs/systems/client/HandleSFMLKeys.hpp

---

# src/ecs/systems/client/HandleSFMLKeys.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::systems](Namespaces/namespaceecs_1_1systems.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** HandleSFMLKeys
*/

#pragma once

#include <functional>
#include "Window.hpp"
#include "World.hpp"
#include "components/client/Controllable.hpp"
#include "components/client/Hitbox.hpp"
#include "components/client/Shootable.hpp"

namespace ecs::systems
{
    std::function<void(World &)> handleSFMLKeys = [](World &world) {
        if (!utils::Window::getInstance().hasFocus())
            return;

        auto &controllables = world.registry.getComponents<component::Controllable>();
        auto const &shootables = world.registry.getComponents<component::Shootable>();

        for (size_t i = 0; i < controllables.size(); ++i) {
            auto &contr = controllables[i];

            if (contr) {
                bool hasMoved = false;
                static ecs::Event::EventType lastEventX;
                static ecs::Event::EventType lastEventY;
                static bool isStopped = false;

                if (sf::Keyboard::isKeyPressed(contr.value().MoveUp)
                    || sf::Keyboard::isKeyPressed(contr.value().MoveUpSecondary)) {
                    hasMoved = true;
                    if (lastEventY != ecs::Event::EventType::MoveUp) {
                        world.pushEvent(ecs::Event(ecs::Event::EventType::MoveUp));
                        lastEventY = ecs::Event::EventType::MoveUp;
                        isStopped = false;
                    }
                } else if (sf::Keyboard::isKeyPressed(contr.value().MoveDown)
                    || sf::Keyboard::isKeyPressed(contr.value().MoveDownSecondary)) {
                    hasMoved = true;
                    if (lastEventY != ecs::Event::EventType::MoveDown) {
                        world.pushEvent(ecs::Event(ecs::Event::EventType::MoveDown));
                        lastEventY = ecs::Event::EventType::MoveDown;
                        isStopped = false;
                    }
                }
                if (sf::Keyboard::isKeyPressed(contr.value().MoveLeft)
                    || sf::Keyboard::isKeyPressed(contr.value().MoveLeftSecondary)) {
                    hasMoved = true;
                    if (lastEventX != ecs::Event::EventType::MoveLeft) {
                        world.pushEvent(ecs::Event(ecs::Event::EventType::MoveLeft));
                        lastEventX = ecs::Event::EventType::MoveLeft;
                        isStopped = false;
                    }
                } else if (sf::Keyboard::isKeyPressed(contr.value().MoveRight)
                    || sf::Keyboard::isKeyPressed(contr.value().MoveRightSecondary)) {
                    hasMoved = true;
                    if (lastEventX != ecs::Event::EventType::MoveRight) {
                        world.pushEvent(ecs::Event(ecs::Event::EventType::MoveRight));
                        lastEventX = ecs::Event::EventType::MoveRight;
                        isStopped = false;
                    }
                }
                if (!hasMoved) {
                    if (!isStopped)
                        world.pushEvent(ecs::Event(ecs::Event::EventType::MoveStop));
                    lastEventX = ecs::Event::EventType::MoveStop;
                    lastEventY = ecs::Event::EventType::MoveStop;
                    isStopped = true;
                }
                if (i < shootables.size()) {
                    auto const &shoot = shootables[i];
                    if (shoot) {
                        if (sf::Keyboard::isKeyPressed(shoot.value().Shoot)
                            || sf::Keyboard::isKeyPressed(shoot.value().ShootSecondary))
                            world.pushEvent(ecs::Event(ecs::Event::EventType::Shoot));
                    }
                }
            }
        }
    };
} // namespace ecs::systems
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
