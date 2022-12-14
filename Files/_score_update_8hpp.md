---
title: src/ecs/systems/client/ScoreUpdate.hpp

---

# src/ecs/systems/client/ScoreUpdate.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::systems](Namespaces/namespaceecs_1_1systems.md)**  |

## Attributes

|                | Name           |
| -------------- | -------------- |
| std::chrono::steady_clock::time_point | **[begin](Files/_score_update_8hpp.md#variable-begin)**  |



## Attributes Documentation

### variable begin

```cpp
static std::chrono::steady_clock::time_point begin = std::chrono::steady_clock::now();
```



## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** R-TYPEMIRROR
** File description:
** Score
*/

#pragma once

#include <functional>
#include <iostream>
#include "World.hpp"
#include "components/client/Text.hpp"
#include "components/Score.hpp"
#include <chrono>

static std::chrono::steady_clock::time_point begin = std::chrono::steady_clock::now();

namespace ecs::systems
{
    std::function<void(World &)> scoreUpdate = [](World &world) {
      auto &texts = world.registry.getComponents<component::Text>();
      auto &scores = world.registry.getComponents<component::Score>();

      for (size_t i = 0; i < texts.size() || i < scores.size(); i++) {
          auto &text = texts[i];
          auto &score = scores[i];

          if (text && score) {
              std::chrono::steady_clock::time_point end = std::chrono::steady_clock::now();
              auto time = std::chrono::duration_cast<std::chrono::milliseconds>(end - begin).count() / 10;
              auto elapsed = std::to_string(time);
              const std::string string = "Score: ";

              text->setContent(0, string);
              text->setContent(1, elapsed);
              score->setScore(time);
          }
      }
    };
} // namespace ecs::systems
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
