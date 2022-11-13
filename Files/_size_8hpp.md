---
title: src/ecs/components/Size.hpp

---

# src/ecs/components/Size.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::Size](Classes/structecs_1_1component_1_1_size.md)** <br>[Size]() component.  |




## Source code

```cpp
#pragma once

namespace ecs::component
{
    struct Size {
        int height;
        int width;
        std::array<char, 4> serialize()
        {
            std::array<char, 4> pos;
            size_t tmp = 0;

            tmp = width >> 8;
            pos[0] = tmp;
            pos[1] = width & 0xff;
            tmp = height >> 8;
            pos[2] = tmp;
            pos[3] = height & 0xff;
            return pos;
        }
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
