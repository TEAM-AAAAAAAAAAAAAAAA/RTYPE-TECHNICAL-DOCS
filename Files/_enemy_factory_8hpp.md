---
title: src/ecs/EnemyFactory.hpp

---

# src/ecs/EnemyFactory.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[ecs::EnemyFactory](Classes/classecs_1_1_enemy_factory.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** EnemyFactory
*/

#pragma once

#include <functional>
#include "World.hpp"
#include "components/Faction.hpp"
#include "components/MovementAI.hpp"
#include <unordered_map>

namespace ecs
{
    class EnemyFactory {
      public:
        enum EnemyType { Battlecruiser, Dreadnought, Fighter, Frigate, Scout, Torpedo, NoodleMonster };

        static void spawnEnemy(ecs::World &world, EnemyType type, int posX, int posY, component::Faction::Factions fac,
            component::MovementAI::AIType movAI)
        {
            _typeGeneratorMap.at(type)(world, posX, posY, fac, movAI);
        }

      private:
        static const std::unordered_map<EnemyType,
            std::function<void(ecs::World &, int, int, component::Faction::Factions, component::MovementAI::AIType)>>
            _typeGeneratorMap;
    };
} // namespace ecs
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
