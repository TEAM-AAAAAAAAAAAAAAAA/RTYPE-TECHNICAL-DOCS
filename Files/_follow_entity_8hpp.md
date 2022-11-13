---
title: src/ecs/components/server/FollowEntity.hpp

---

# src/ecs/components/server/FollowEntity.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::FollowEntity](Classes/structecs_1_1component_1_1_follow_entity.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** FollowEntity
*/

#pragma once

#include <cstddef>

namespace ecs::component
{
    struct FollowEntity {
        std::size_t entityId;
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
