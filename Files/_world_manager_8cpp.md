---
title: src/ecs/WorldManager.cpp

---

# src/ecs/WorldManager.cpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** WorldManager
*/

#include "WorldManager.hpp"

namespace ecs
{
    WorldManager &WorldManager::getInstance()
    {
        static WorldManager _Instance;
        return _Instance;
    }
}
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100
