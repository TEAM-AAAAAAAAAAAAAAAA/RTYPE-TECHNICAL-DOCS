---
title: src/ecs/systems/client/Animate.hpp

---

# src/ecs/systems/client/Animate.hpp



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
** Draw
*/

#pragma once

#include <functional>
#include <iostream>
#include "SFML/Graphics.hpp"
#include "World.hpp"
#include "components/Position.hpp"
#include "components/Size.hpp"
#include "components/client/Animated.hpp"
#include "components/client/Drawable.hpp"

namespace ecs::systems
{
    std::function<void(World &)> animate = [](World &world) {
        auto &animateds = world.registry.getComponents<component::Animated>();

        using chrono = std::chrono::high_resolution_clock;
        using chronoDuration = std::chrono::duration<double, std::milli>;
        for (size_t i = 0; i < animateds.size(); ++i) {
            auto &anim = animateds[i];

            if (anim) {
                if (chrono::now().time_since_epoch().count() - anim.value().lastSwitch
                    > static_cast<size_t>(anim.value().getFrame().delay) * 1000000) {
                    anim.value().nextFrame();
                    anim.value().lastSwitch = chrono::now().time_since_epoch().count();
                }
            }
        }
    };
} // namespace ecs::systems
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
