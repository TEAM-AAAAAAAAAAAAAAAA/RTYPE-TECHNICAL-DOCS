---
title: src/client/NetworkClient.cpp

---

# src/client/NetworkClient.cpp



## Namespaces

| Name           |
| -------------- |
| **[network](Namespaces/namespacenetwork.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** rtype
** File description:
** Client
*/

#include "NetworkClient.hpp"
#include <iostream>

namespace network
{
    Client &Client::getInstance()
    {
        static Client _Instance;
        return _Instance;
    }

} // namespace network
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100
