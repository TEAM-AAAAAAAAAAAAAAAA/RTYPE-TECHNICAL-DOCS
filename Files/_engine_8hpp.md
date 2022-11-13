---
title: src/ecs/Engine.hpp

---

# src/ecs/Engine.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[ecs::Engine](Classes/classecs_1_1_engine.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** Engine
*/

#pragma once

#include <filesystem>
#include <functional>
#include <memory>
#include "Engine.hpp"
#include "Registry.hpp"
#include "Window.hpp"
#include "World.hpp"
#include "WorldManager.hpp"

namespace ecs
{
    class Engine {
      public:
        explicit Engine()
        {
            ecs::WorldManager::setWorldSwitchReady(false);
            ecs::World initWorld;
            ecs::WorldManager::getInstance()._currentWorld = std::make_unique<ecs::World>(initWorld);
        }

        void run()
        {
            while (utils::Window::isOpen()) {
                ecs::WorldManager::getWorld().runSystems();
                if (ecs::WorldManager::isWorldSwitchReady())
                    ecs::WorldManager::switchWorlds();
            }
        }
    };
} // namespace ecs
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
