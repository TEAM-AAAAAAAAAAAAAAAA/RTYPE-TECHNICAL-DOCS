---
title: src/ecs/systems/client/HandleParallaxBounds.hpp

---

# src/ecs/systems/client/HandleParallaxBounds.hpp



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
** HandleParallaxBounds
*/

#pragma once

#include <functional>
#include <iostream>
#include "World.hpp"
#include "components/client/Parallax.hpp"
#include "components/Position.hpp"

namespace ecs::systems
{
    std::function<void(World &)> HandleParallaxBounds = [](World &world) {
        auto &parallaxes = world.registry.getComponents<component::Parallax>();
        auto &positions = world.registry.getComponents<component::Position>();

        for (size_t i = 0; i < parallaxes.size() && i < positions.size(); i++) {
            if (!parallaxes[i] || !positions[i])
                continue;
            if (positions[i].value().x < parallaxes[i].value().threshold) {
                positions[i].value().x += parallaxes[i].value().position;
            }
        }
    };
}
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100
