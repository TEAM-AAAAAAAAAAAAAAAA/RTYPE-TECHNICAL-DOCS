---
title: src/ecs/systems/RunMovementAI.hpp

---

# src/ecs/systems/RunMovementAI.hpp



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
** RunMovementAI
*/

#pragma once

#include <chrono>
#include <functional>
#include <iostream>
#include "World.hpp"
#include "components/Direction.hpp"
#include "components/MovementAI.hpp"

namespace ecs::systems
{
    std::function<void(World &)> runMovementAI = [](World &world) {
        auto &directions = world.registry.getComponents<component::Direction>();
        auto &movementAIs = world.registry.getComponents<component::MovementAI>();

        using chrono = std::chrono::high_resolution_clock;
        using chronoDuration = std::chrono::duration<double, std::milli>;

        for (size_t i = 0; i < directions.size() && i < movementAIs.size(); ++i) {
            auto &dir = directions[i];
            auto &movAI = movementAIs[i];

            if (dir && movAI) {
                if ((chrono::now().time_since_epoch().count() - movAI.value().getLastMovement()) / 10000000
                    > static_cast<size_t>(movAI.value().getDelay())) {
                    auto &tmpDir = movAI.value().getNextDirection();
                    dir.value().x = tmpDir.first;
                    dir.value().y = tmpDir.second;
                    dir.value().hasMoved = true;
                    movAI.value().setLastMovement(chrono::now().time_since_epoch().count());
                }
            }
        };
    };
} // namespace ecs::systems
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
