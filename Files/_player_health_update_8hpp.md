---
title: src/ecs/systems/server/PlayerHealthUpdate.hpp

---

# src/ecs/systems/server/PlayerHealthUpdate.hpp



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
** playerHealthUpdate
*/

#pragma once

#include <functional>
#include <iostream>
#include "Constant.hpp"
#include "Entity.hpp"
#include "World.hpp"
#include "components/NetworkId.hpp"
#include "components/Position.hpp"

namespace ecs::systems
{
    std::function<void(World &)> playerHealthUpdate = [](World &world) {
        auto &healths = world.registry.getComponents<component::Health>();
        auto &networkId = world.registry.getComponents<component::NetworkId>();
        auto &entity = world.registry.getComponents<component::EntityType>();
        for (size_t i = 0; i < healths.size(); ++i) {
            auto &health = healths[i];
            if (health && health.value().health != health.value().lastHealth) {
                if (i < entity.size() && i < networkId.size()) {
                    auto &type = entity[i];
                    auto &id = networkId[i];
                    if (type && id && type.value().type == component::EntityType::Types::Player) {
                        health.value().lastHealth = health.value().health;
                        std::array<char, 2> idBin = id.value().serialize();
                        network::Message msg;
                        msg[0] = utils::constant::getPacketTypeKey(utils::constant::PacketType::HEALTH_UPDATE);
                        msg[1] = idBin[0];
                        msg[2] = idBin[1];
                        msg[3] = health.value().health;
                        network::Server::getOutgoingMessages().push(
                            network::ServerMessage(msg, std::vector<unsigned int>()));
                    }
                }
            }
        }
    };
} // namespace ecs::systems
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
