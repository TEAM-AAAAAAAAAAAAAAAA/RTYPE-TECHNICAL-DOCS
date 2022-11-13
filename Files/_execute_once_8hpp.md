---
title: src/ecs/systems/client/ExecuteOnce.hpp

---

# src/ecs/systems/client/ExecuteOnce.hpp



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
** ExecuteOnce
*/

#pragma once

#include <functional>
#include "../client/NetworkClient.hpp"
#include "World.hpp"

namespace ecs::systems
{
    std::function<void(World &)> executeOnce = [](World &world) {
        static bool executed = false;

        if (!executed) {
            network::Message msg;
            msg.fill(0);
            network::Client::connect();
            network::Client::getOutgoingMessages().push(msg);
            executed = true;
        }
    };
} // namespace ecs::systems
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100
