---
title: src/ecs/systems/ManageClientEvents.hpp

---

# src/ecs/systems/ManageClientEvents.hpp



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
** ManageClientEvents
*/

#pragma once

#include <functional>
#include "../client/NetworkClient.hpp"
#include "Constant.hpp"
#include "Event.hpp"
#include "World.hpp"
#include "components/Direction.hpp"
#include "components/Faction.hpp"
#include "components/Weapon.hpp"
#include "components/client/Controllable.hpp"
#include "components/client/Hitbox.hpp"
#include "components/client/Shootable.hpp"
#include "components/server/Projectile.hpp"

namespace ecs::systems
{
    std::function<void(World &)> manageClientEvents = [](World &world) {
        while (world.getEvent() != ecs::Event::EventType::Null) {

#pragma region Player Movement
            if (world.getEvent() == ecs::Event::EventType::MoveUp || world.getEvent() == ecs::Event::EventType::MoveLeft
                || world.getEvent() == ecs::Event::EventType::MoveDown
                || world.getEvent() == ecs::Event::EventType::MoveRight
                || world.getEvent() == ecs::Event::EventType::MoveStop) {
                auto &directions = world.registry.getComponents<component::Direction>();
                auto &controllables = world.registry.getComponents<component::Controllable>();

                for (size_t i = 0; i < directions.size() && i < controllables.size(); ++i) {
                    auto &dir = directions[i];
                    auto &con = controllables[i];
                    if (dir && con) {
                        int x = dir.value().x;
                        int y = dir.value().y;
                        if (world.getEvent() == ecs::Event::EventType::MoveStop) {
                            dir.value().x = 0;
                            dir.value().y = 0;
                        } else if (world.getEvent() == ecs::Event::EventType::MoveUp) {
                            dir.value().y = -1;
                        } else if (world.getEvent() == ecs::Event::EventType::MoveLeft) {
                            dir.value().x = -1;
                        } else if (world.getEvent() == ecs::Event::EventType::MoveDown) {
                            dir.value().y = 1;
                        } else if (world.getEvent() == ecs::Event::EventType::MoveRight) {
                            dir.value().x = 1;
                        }
                        if (x != dir.value().x || y != dir.value().y)
                            dir.value().hasMoved = true;
                    }
                }
            }
#pragma endregion

#pragma region Bullet Shoot
            else if (world.getEvent() == ecs::Event::EventType::Shoot) {
                network::Message msg;
                msg.fill(0);
                msg.at(0) = utils::constant::getPacketTypeKey(utils::constant::PacketType::PLAYER_SHOT);
                network::Client::getOutgoingMessages().push(msg);
            }
#pragma endregion
            world.popEvent();
        }
    };
} // namespace ecs::systems
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
