---
title: src/ecs/systems/server/Waves.hpp

---

# src/ecs/systems/server/Waves.hpp



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
** Waves
*/

#pragma once

#include <functional>
#include "Constant.hpp"
#include "EnemyFactory.hpp"
#include "World.hpp"
#include "WorldManager.hpp"

namespace ecs::systems
{
    std::function<void(World &)> waves = [](World &world) {
        static std::size_t lastWave = 0;
        static int waveCounter = 0;
        auto const &factions = ecs::WorldManager::getWorld().registry.getComponents<ecs::component::Faction>();
        bool enemiesAlive = false;

        for (std::size_t i = 0; i < factions.size(); i++) {
            auto const &fac = factions[i];

            if (fac) {
                if (fac.value().faction != ecs::component::Faction::Factions::Chefs) {
                    enemiesAlive = true;
                }
            }
        }
        if (!enemiesAlive || utils::constant::chrono::now().time_since_epoch().count() - 100000000000 > lastWave) {
            waveCounter++;
            std::cout << "next wave (" << waveCounter << ")" << std::endl;
            if (waveCounter % 10 == 0) {
                ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(),
                    ecs::EnemyFactory::EnemyType::NoodleMonster, utils::constant::mapWidth - 200, 400,
                    ecs::component::Faction::Amalgam, ecs::component::MovementAI::AIType::LongUpDown);
            } else {
                if (waveCounter % 1 == 0) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Scout,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::QuickUpDown);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Scout,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::ClockwiseSmall);
                }
                if (waveCounter % 2 == 0) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Fighter,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::AntiClockwiseBig);
                }
                if (waveCounter % 3 == 0) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Fighter,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::Idle);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Fighter,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::QuickUpDown);
                }
                if (waveCounter % 4 == 0) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Frigate,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::AntiClockwiseSmall);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Frigate,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::ClockwiseBig);
                }
                if (waveCounter % 5 == 0) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(),
                        ecs::EnemyFactory::EnemyType::Battlecruiser,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::AntiClockwiseBig);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Frigate,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::LongLeftRight);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Fighter,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::LongLeftRight);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Fighter,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::Idle);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Scout,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::LongUpDown);
                }
                if (waveCounter >= 6) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(),
                        ecs::EnemyFactory::EnemyType::Dreadnought,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::Idle);
                }
                if (waveCounter % 7 == 0) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Torpedo,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::LongUpDown);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Torpedo,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::LongUpDown);
                }
                if (waveCounter % 8 == 0) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Torpedo,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::ClockwiseSmall);
                }
                if (waveCounter % 9 == 0) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(),
                        ecs::EnemyFactory::EnemyType::Battlecruiser,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::AntiClockwiseBig);
                }
                if (waveCounter >= 11) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(),
                        ecs::EnemyFactory::EnemyType::Dreadnought,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Uranus,
                        ecs::component::MovementAI::AIType::Idle);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Scout,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Janitor,
                        ecs::component::MovementAI::AIType::QuickUpDown);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Scout,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Janitor,
                        ecs::component::MovementAI::AIType::ClockwiseSmall);
                }
                if (waveCounter >= 12) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Fighter,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Janitor,
                        ecs::component::MovementAI::AIType::AntiClockwiseBig);
                }
                if (waveCounter >= 14) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Frigate,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Janitor,
                        ecs::component::MovementAI::AIType::AntiClockwiseSmall);
                }
                if (waveCounter >= 15) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(),
                        ecs::EnemyFactory::EnemyType::Battlecruiser,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Janitor,
                        ecs::component::MovementAI::AIType::AntiClockwiseBig);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Frigate,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Janitor,
                        ecs::component::MovementAI::AIType::LongLeftRight);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Fighter,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Janitor,
                        ecs::component::MovementAI::AIType::LongLeftRight);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Fighter,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Janitor,
                        ecs::component::MovementAI::AIType::Idle);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Scout,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Janitor,
                        ecs::component::MovementAI::AIType::LongUpDown);
                }
                if (waveCounter >= 16) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(),
                        ecs::EnemyFactory::EnemyType::Dreadnought,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Janitor,
                        ecs::component::MovementAI::AIType::Idle);
                }
                if (waveCounter >= 17) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Torpedo,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Janitor,
                        ecs::component::MovementAI::AIType::LongUpDown);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Torpedo,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Janitor,
                        ecs::component::MovementAI::AIType::LongUpDown);
                }
                if (waveCounter >= 18) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(),
                        ecs::EnemyFactory::EnemyType::Battlecruiser,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Janitor,
                        ecs::component::MovementAI::AIType::ClockwiseSmall);
                }
                if (waveCounter >= 19) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(),
                        ecs::EnemyFactory::EnemyType::Battlecruiser,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Janitor,
                        ecs::component::MovementAI::AIType::AntiClockwiseBig);
                }
                if (waveCounter >= 21) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(),
                        ecs::EnemyFactory::EnemyType::Dreadnought,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Janitor,
                        ecs::component::MovementAI::AIType::Idle);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Scout,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Alien,
                        ecs::component::MovementAI::AIType::QuickUpDown);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Scout,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Alien,
                        ecs::component::MovementAI::AIType::ClockwiseSmall);
                }
                if (waveCounter >= 22) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Fighter,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Alien,
                        ecs::component::MovementAI::AIType::AntiClockwiseBig);
                }
                if (waveCounter >= 24) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Frigate,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Alien,
                        ecs::component::MovementAI::AIType::AntiClockwiseSmall);
                }
                if (waveCounter >= 25) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(),
                        ecs::EnemyFactory::EnemyType::Battlecruiser,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Alien,
                        ecs::component::MovementAI::AIType::AntiClockwiseBig);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Frigate,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Alien,
                        ecs::component::MovementAI::AIType::LongLeftRight);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Fighter,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Alien,
                        ecs::component::MovementAI::AIType::LongLeftRight);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Fighter,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Alien,
                        ecs::component::MovementAI::AIType::Idle);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Scout,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Alien,
                        ecs::component::MovementAI::AIType::LongUpDown);
                }
                if (waveCounter >= 26) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(),
                        ecs::EnemyFactory::EnemyType::Dreadnought,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Alien,
                        ecs::component::MovementAI::AIType::Idle);
                }
                if (waveCounter >= 27) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Torpedo,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Alien,
                        ecs::component::MovementAI::AIType::LongUpDown);
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(), ecs::EnemyFactory::EnemyType::Torpedo,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Alien,
                        ecs::component::MovementAI::AIType::LongUpDown);
                }
                if (waveCounter >= 28) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(),
                        ecs::EnemyFactory::EnemyType::Battlecruiser,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Alien,
                        ecs::component::MovementAI::AIType::ClockwiseSmall);
                }
                if (waveCounter >= 29) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(),
                        ecs::EnemyFactory::EnemyType::Battlecruiser,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Alien,
                        ecs::component::MovementAI::AIType::AntiClockwiseBig);
                }
                if (waveCounter >= 31) {
                    ecs::EnemyFactory::spawnEnemy(ecs::WorldManager::getWorld(),
                        ecs::EnemyFactory::EnemyType::Dreadnought,
                        200 + std::rand() % (utils::constant::mapWidth - 600),
                        std::rand() % (utils::constant::mapHeight - 200), ecs::component::Faction::Alien,
                        ecs::component::MovementAI::AIType::Idle);
                }
            }
            lastWave = utils::constant::chrono::now().time_since_epoch().count();
        }
    };
}
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
