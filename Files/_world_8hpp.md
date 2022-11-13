---
title: src/ecs/World.hpp

---

# src/ecs/World.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[ecs::World](Classes/classecs_1_1_world.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** World
*/

#pragma once

#include <queue>
#include "Event.hpp"
#include "Registry.hpp"

namespace ecs
{
    class World {
      public:
        World() {};

        void runSystems()
        {
            for (auto &&i : _systems) {
                i(*this);
            }
        }

        void addSystem(const std::function<void(World &)> &system) { _systems.push_back(system); }

        void pushEvent(const ecs::Event event) { _events.push(event); }

        const ecs::Event getEvent() const
        {
            if (_events.empty())
                return {ecs::Event::EventType::Null};
            return _events.front();
        }

        const ecs::Event popEvent()
        {
            if (_events.empty())
                return {ecs::Event::EventType::Null};
            ecs::Event event = _events.front();
            _events.pop();
            return event;
        }

        Registry registry;

      private:
        std::vector<std::function<void(World &)>> _systems;

        std::queue<ecs::Event> _events;
    };
} // namespace ecs
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
