---
title: src/ecs/components/Faction.hpp

---

# src/ecs/components/Faction.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::Faction](Classes/structecs_1_1component_1_1_faction.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** Faction
*/

#pragma once

namespace ecs::component
{
    struct Faction {
        enum Factions {
            None,
            Chefs,
            Uranus,
            Janitor,
            Alien,
            Amalgam,
        };

        Faction(Factions faction = Factions::None) : faction(faction) {}

        Factions faction;
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100
