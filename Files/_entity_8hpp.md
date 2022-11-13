---
title: src/ecs/Entity.hpp

---

# src/ecs/Entity.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[ecs::Entity](Classes/classecs_1_1_entity.md)**  |




## Source code

```cpp
#pragma once

#include <cstddef>

namespace ecs
{
    class Entity {
      public:
        friend class Registry;

        explicit operator size_t &() { return _id; }
        explicit operator size_t() const { return _id; }

      private:
        explicit Entity(size_t id) : _id(id) {}

        size_t &operator=(const std::size_t &id)
        {
            _id = id;
            return _id;
        }

        std::size_t _id;
    };
} // namespace ecs
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100
