---
title: src/ecs/components/Score.hpp

---

# src/ecs/components/Score.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::Score](Classes/structecs_1_1component_1_1_score.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, by hourcadettej on 11/11/22.
** rtype
** File description:
** rtype
*/

#pragma once
#include <string>

namespace ecs::component {
    struct Score {

        Score(size_t score = 0) : _score(score) {}

        inline void setScore(size_t score) {_score = score;}
        inline size_t getScore() const {return _score;}

      private:
        size_t _score;
    };
};
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
