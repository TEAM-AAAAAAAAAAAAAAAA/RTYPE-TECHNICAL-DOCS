---
title: src/ecs/components/EntityType.hpp

---

# src/ecs/components/EntityType.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::EntityType](Classes/structecs_1_1component_1_1_entity_type.md)** <br>[EntityType]() component.  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** EntityType
*/

#pragma once

namespace ecs::component
{
    struct EntityType {
        enum Types {
            Player,
            OtherPlayer,
            PlayerBot,
            Bullet,
            EnergySphere,
            Laser,
            Rocket,
            Asteroid,
            UranusBattlecruiser,
            UranusDreadnought,
            UranusFighter,
            UranusFrigate,
            UranusScout,
            UranusTorpedo,
            JanitorBattlecruiser,
            JanitorDreadnought,
            JanitorFighter,
            JanitorFrigate,
            JanitorScout,
            JanitorTorpedo,
            AlienBattlecruiser,
            AlienDreadnought,
            AlienFighter,
            AlienFrigate,
            AlienScout,
            AlienTorpedo,
            NoodleMonster,
        };
        EntityType(char type) : type(static_cast<Types>(type)) {}
        EntityType(Types type) : type(type) {}
        Types type;
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
