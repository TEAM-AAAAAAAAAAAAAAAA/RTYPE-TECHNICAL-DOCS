---
title: src/ecs/components/server/AttackAI.hpp

---

# src/ecs/components/server/AttackAI.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::AttackAI](Classes/structecs_1_1component_1_1_attack_a_i.md)** <br>[AttackAI]() component.  |
| struct | **[ecs::component::AttackAI::AI](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i.md)** <br>The [AI]() structure where the pattern of the entity is defined.  |
| struct | **[ecs::component::AttackAI::AI::Pattern](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i_1_1_pattern.md)** <br>The [Pattern]() structure contains a std::functions and a reloadTime. Patterns are created in the CPP file.  |
| struct | **[ecs::component::AttackAI::Action](Classes/structecs_1_1component_1_1_attack_a_i_1_1_action.md)** <br>The [Action]() structure contains the prototypes of the functions used by patterns.  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** AttackAI
*/

#pragma once

#include <algorithm>
#include <functional>
#include <vector>
#include "World.hpp"
#include "components/EntityType.hpp"
#include "components/Faction.hpp"
#include <unordered_map>

namespace ecs::component
{
    struct AttackAI {
      public:
        enum AIType { None, Battlecruiser, Dreadnought, Fighter, Frigate, Scout, Torpedo, NoodleMonster, PlayerBot };

        enum PatternType {
            Wait,
            WaitShort,
            WaitLong,
            ShootBullet,
            ShootEnergySphere,
            ShootEnergySphereFast,
            ShootLaser,
            ShootRocket,
            InvokeAllies,
            InvokeAnyone,
            SpawnAsteroids,
            PlayerBotLaser
        };

        size_t lastAttack;
        size_t lastAttackDelay;

        struct AI {
            struct Pattern {
                Pattern(short reloadTime, std::function<void(const std::size_t)> pattern)
                    : reloadTime(reloadTime), _function(pattern)
                {
                }

                void run(const std::size_t &shooter) const { _function(shooter); }

                short reloadTime;

                std::function<void(const std::size_t)> _function;
            };

            AI(std::vector<PatternType> pattern) : _thisPatterns(pattern), currentAttack(0) {}

            AI(const AI &other) : currentAttack(other.currentAttack), _thisPatterns(other._thisPatterns) {}

            inline const std::vector<PatternType> &getPatterns() const { return _thisPatterns; }

            static const std::unordered_map<PatternType, Pattern> patterns;

          private:
            short currentAttack;
            std::vector<PatternType> _thisPatterns;
        };

        struct Action {
            static void waitAttack(const std::size_t shooter);
            static void shootBulletAttack(const std::size_t shooter);
            static void shootEnerySphereAttack(const std::size_t shooter);
            static void shootLaserAttack(const std::size_t shooter);
            static void shootRocketAttack(const std::size_t shooter);
            static void invokeAlliesAttack(const std::size_t shooter);
            static void spawnAsteroidsAttack(const std::size_t shooter);
            static void invokeAnyoneAttack(const std::size_t shooter);
            static void playerBotLaser(const std::size_t shooter);

          private:
            static void spawnNewBullet(component::EntityType::Types type, int posX, int posY, char dirX, char dirY,
                int sizeX, int sizeY, int velX, int velY, int dmg, ecs::component::Faction::Factions fac,
                int bulletHealth = 1);
        };

        AttackAI(const AIType &type = None) : _thisAI(findAI(type)), lastAttack(0), lastAttackDelay(0) {}

        const AttackAI::AI::Pattern &getRandomAttack() const
        {
            int attack = _thisAI.getPatterns().at(std::rand() % _thisAI.getPatterns().size());
            return AI::patterns.at(static_cast<PatternType>(attack));
        }

      private:
        AI _thisAI;

        inline const AI &findAI(const AIType &type) { return _aiVector.at(type); }

        static const std::unordered_map<AIType, AI> _aiVector;
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100
