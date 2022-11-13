---
title: src/ecs/components/client/Hitbox.hpp

---

# src/ecs/components/client/Hitbox.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::Hitbox](Classes/structecs_1_1component_1_1_hitbox.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, by hourcadettej on 10/29/22.
** rtype
** File description:
** rtype
*/

#pragma once

#include "SFML/Window/Keyboard.hpp"

namespace ecs::component
{
    struct Hitbox {
        explicit Hitbox() : enableHitBox(false){}

        bool enableHitBox;

        inline void switchHitBox() { enableHitBox = !enableHitBox;};

    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
