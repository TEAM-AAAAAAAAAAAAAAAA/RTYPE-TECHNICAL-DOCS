---
title: src/ecs/WorldManager.hpp

---

# src/ecs/WorldManager.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[ecs::WorldManager](Classes/classecs_1_1_world_manager.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** WorldManager
*/

#pragma once
#include <memory>
#include "World.hpp"

namespace ecs
{
    class Engine;

    class WorldManager {
      public:
        friend Engine;
        ~WorldManager() = default;

        static void setWorldSwitchReady(bool isReady = true) { getInstance()._worldSwitchReady = isReady; }

        static ecs::World &getWorld() { return *getInstance()._currentWorld; }

        static void setWaitingWorld(std::function<World()> worldGen, bool worldSwitchReady = true)
        {
            if (getInstance()._waitingWorld)
                getInstance()._waitingWorld.release();
            getInstance()._waitingWorld = std::make_unique<ecs::World>(worldGen());
            getInstance()._worldSwitchReady = worldSwitchReady;
        }

        static void setWorldSwitchReady() { getInstance()._worldSwitchReady = true; }

      private:
        bool _worldSwitchReady;
        std::unique_ptr<ecs::World> _currentWorld;
        std::unique_ptr<ecs::World> _waitingWorld;


        static WorldManager &getInstance();

        [[nodiscard]] static bool isWorldSwitchReady() { return getInstance()._worldSwitchReady; }

        static void switchWorlds()
        {
            if (getInstance()._waitingWorld)
                getInstance()._currentWorld.swap(getInstance()._waitingWorld);
            getInstance()._worldSwitchReady = false;
        }
    };
} // namespace ecs
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
