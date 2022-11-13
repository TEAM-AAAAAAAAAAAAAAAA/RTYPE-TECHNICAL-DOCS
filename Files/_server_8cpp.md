---
title: src/server/Server.cpp

---

# src/server/Server.cpp



## Namespaces

| Name           |
| -------------- |
| **[network](Namespaces/namespacenetwork.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** Server
*/

#include "Server.hpp"

namespace network
{
    Server &Server::getInstance()
    {
        static Server _Instance;
        return _Instance;
    }
} // namespace network
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
