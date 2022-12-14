---
title: src/ecs/systems/server/HandleIncomingMessage.hpp

---

# src/ecs/systems/server/HandleIncomingMessage.hpp



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
** HandleIncomingMessage
*/

#pragma once

#include <functional>
#include <iostream>
#include "../server/Server.hpp"
#include "Constant.hpp"
#include "World.hpp"
#include "components/Direction.hpp"
#include "components/EntityType.hpp"
#include "components/Faction.hpp"
#include "components/Health.hpp"
#include "components/NetworkId.hpp"
#include "components/Position.hpp"
#include "components/Size.hpp"
#include "components/Velocity.hpp"
#include "components/Weapon.hpp"
#include "components/server/Projectile.hpp"
#include "components/server/FollowEntity.hpp"
#include "components/server/AttackAI.hpp"

namespace ecs::systems
{
    static std::map<unsigned int, size_t> clientNumToId = {};

    static void createPlayer(World &world, network::ClientMessage &msg)
    {
        ecs::Entity newPlayer = world.registry.spawn_entity();

        world.registry.addComponent<ecs::component::Position>(newPlayer, {50, utils::constant::mapHeight / 2});
        world.registry.addComponent<ecs::component::Velocity>(newPlayer, {5, 5});
        world.registry.addComponent<ecs::component::Size>(newPlayer, {32, 64});
        world.registry.addComponent<ecs::component::Direction>(newPlayer, {0, 0});
        world.registry.addComponent<ecs::component::EntityType>(newPlayer, {ecs::component::EntityType::Types::Player});
        world.registry.addComponent<ecs::component::Weapon>(newPlayer, {100, 50, 10, {20, 20}});
        world.registry.addComponent<ecs::component::Health>(newPlayer, {utils::constant::maxPlayerHealth});
        world.registry.addComponent<ecs::component::NetworkId>(newPlayer, {static_cast<size_t>(newPlayer)});
        world.registry.addComponent<ecs::component::Faction>(newPlayer, {ecs::component::Faction::Factions::Chefs});

        ecs::Entity playerBot = world.registry.spawn_entity();

        world.registry.addComponent<ecs::component::Position>(playerBot, {20, 5});
        world.registry.addComponent<ecs::component::Size>(playerBot, {16, 32});
        world.registry.addComponent<ecs::component::EntityType>(playerBot, {ecs::component::EntityType::Types::PlayerBot});
        world.registry.addComponent<ecs::component::Velocity>(playerBot, {0, 0});
        world.registry.addComponent<ecs::component::Direction>(playerBot, {0, 0});
        world.registry.addComponent<ecs::component::Health>(playerBot, {100});
        world.registry.addComponent<ecs::component::NetworkId>(playerBot, {static_cast<size_t>(playerBot)});
        world.registry.addComponent<ecs::component::Faction>(playerBot, {ecs::component::Faction::Factions::Chefs});
        world.registry.addComponent<ecs::component::FollowEntity>(playerBot, {static_cast<std::size_t>(newPlayer)});
        world.registry.addComponent<ecs::component::AttackAI>(playerBot, {component::AttackAI::AIType::PlayerBot});

        clientNumToId[msg.second] = static_cast<size_t>(newPlayer);
        network::Message message;
        message.fill(0);
        message[1] = static_cast<size_t>(newPlayer) >> 8;
        message[2] = static_cast<size_t>(newPlayer) & 0xFF;
        network::Server::getOutgoingMessages().push(network::ServerMessage(message, std::vector<unsigned int>()));
    }

    static void movePlayer(World &world, network::ClientMessage &msg)
    {
        auto &directions = world.registry.getComponents<component::Direction>();
        auto &networkIds = world.registry.getComponents<component::NetworkId>();

        for (size_t i = 0; i < directions.size() && i < networkIds.size(); ++i) {
            auto &dir = directions[i];
            auto &id = networkIds[i];

            if (dir && id) {
                if (clientNumToId[msg.second] == id.value().id) {
                    dir.value().x = (int)msg.first[1];
                    dir.value().y = (int)msg.first[2];
                    return;
                }
            }
        }
    }

    static void playerShoot(World &world, network::ClientMessage &msg)
    {
        auto &networkIds = world.registry.getComponents<component::NetworkId>();
        auto const &positions = world.registry.getComponents<component::Position>();
        auto &weapons = world.registry.getComponents<component::Weapon>();
        auto const &factions = world.registry.getComponents<component::Faction>();

        for (size_t i = 0; i < networkIds.size() && i < positions.size() && i < weapons.size() && i < factions.size();
             ++i) {
            auto &id = networkIds[i];

            if (id
                && clientNumToId.find(msg.second) != clientNumToId.end() & clientNumToId[msg.second] == id.value().id) {
                auto &pos = positions[i];
                auto &weapon = weapons[i];
                auto &fac = factions[i];

                if (pos && weapon && fac) {
                    auto elapsed = utils::constant::chrono::now().time_since_epoch().count() - weapon.value().lastShoot;
                    if (weapon.value().hasSuper && elapsed > weapon.value().superLoadingTime) {
                        weapon.value().lastShoot = utils::constant::chrono::now().time_since_epoch().count();
                    } else if (elapsed > weapon.value().shootDelay) {
                        weapon.value().lastShoot = utils::constant::chrono::now().time_since_epoch().count();
                        ecs::Entity bullet = world.registry.spawn_entity();
                        world.registry.addComponent<ecs::component::EntityType>(
                            bullet, {component::EntityType::Bullet});
                        world.registry.addComponent<ecs::component::NetworkId>(bullet, {static_cast<size_t>(bullet)});
                        world.registry.addComponent<ecs::component::Direction>(bullet, {1, 0});
                        world.registry.addComponent<ecs::component::Position>(bullet, {pos.value().x, pos.value().y});
                        world.registry.addComponent<ecs::component::Size>(
                            bullet, {weapon.value().projSize.first, weapon.value().projSize.second});
                        world.registry.addComponent<ecs::component::Velocity>(bullet, {weapon.value().projSpeed, 0});
                        world.registry.addComponent<ecs::component::Projectile>(bullet, {weapon.value().damage});
                        ecs::component::Faction::Factions fac = ecs::component::Faction::Factions::None;
                        if (i < factions.size() && factions[i])
                            fac = factions[i].value().faction;
                        world.registry.addComponent<ecs::component::Faction>(bullet, {fac});
                        world.registry.addComponent<ecs::component::Health>(bullet, {1});
                    }
                }
            }
        };
    }

    static std::unordered_map<char, std::function<void(World &, network::ClientMessage &msg)>> packetTypeFunction = {
        {0, createPlayer}, {utils::constant::PLAYER_MOVE, movePlayer}, {utils::constant::PLAYER_SHOT, playerShoot}};

    std::function<void(World &)> HandleIncomingMessages = [](World &world) {
        while (!network::Server::GetReceivedMessages().empty()) {
            network::ClientMessage msg = network::Server::GetReceivedMessages().pop();
            if (packetTypeFunction.find(msg.first[0]) != packetTypeFunction.end())
                packetTypeFunction[msg.first[0]](world, msg);
        }
    };
} // namespace ecs::systems
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
