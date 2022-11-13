---
title: src/client/AssetLoader.cpp

---

# src/client/AssetLoader.cpp



## Namespaces

| Name           |
| -------------- |
| **[asset](Namespaces/namespaceasset.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** Server
*/

#include "AssetLoader.hpp"

namespace asset
{
    AssetLoader &AssetLoader::getInstance()
    {
        static AssetLoader _Instance;
        return _Instance;
    }
}; // namespace asset
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100
