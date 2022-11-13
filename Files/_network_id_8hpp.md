---
title: src/ecs/components/NetworkId.hpp

---

# src/ecs/components/NetworkId.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::NetworkId](Classes/structecs_1_1component_1_1_network_id.md)** <br>[NetworkId]() component related to the entity sent to the client.  |




## Source code

```cpp
/*
** EPITECH PROJECT, by hourcadettej on 10/3/22.
** rtype
** File description:
** rtype
*/

#pragma once
#include <array>
#include <cstddef>

namespace ecs::component
{
    struct NetworkId {
        NetworkId() : id(_last_id + 1) { _last_id++; }

        NetworkId(size_t id) : id(id) {}

        size_t id;
        std::array<char, 2> serialize()
        {
            std::array<char, 2> arr;
            size_t tmp = 0;

            tmp = id >> 8;
            arr[0] = tmp;
            arr[1] = id & 0xff;
            return arr;
        }

      private:
        static size_t _last_id;
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
