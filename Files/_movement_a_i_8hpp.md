---
title: src/ecs/components/MovementAI.hpp

---

# src/ecs/components/MovementAI.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::MovementAI](Classes/structecs_1_1component_1_1_movement_a_i.md)** <br>[MovementAI]() component.  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** MovementAI
*/

#pragma once

#include <algorithm>
#include <vector>
#include <unordered_map>

namespace ecs::component
{
    struct MovementAI {
      public:
        enum AIType { Idle, QuickUpDown, LongUpDown, QuickLeftRight, LongLeftRight, ClockwiseSmall, ClockwiseBig, AntiClockwiseSmall, AntiClockwiseBig };

        MovementAI(const AIType &type = Idle) : _thisAI(findAI(type)) {}

        inline const std::pair<char, char> &getNextDirection()
        {
            if (_thisAI.currentIndex < _thisAI.direction.size() - 1) {
                _thisAI.currentIndex++;
                return _thisAI.direction[_thisAI.currentIndex - 1];
            } else {
                _thisAI.currentIndex = 0;
                return _thisAI.direction[_thisAI.direction.size() - 1];
            }
        }

        inline const std::size_t &getDelay() const { return _thisAI.delay; }

        inline const std::size_t &getLastMovement() const { return _thisAI.lastMovement; }

        inline void setLastMovement(const std::size_t &lastMovement) { _thisAI.lastMovement = lastMovement; }

      private:
        struct AI {
            AI(std::vector<std::pair<char, char>> direction, std::size_t delay)
                : direction(direction), delay(delay), currentIndex(0)
            {
            }

            AI(const AI &other) : currentIndex(other.currentIndex), delay(other.delay), direction(other.direction) {}

            std::vector<std::pair<char, char>> direction;
            int currentIndex;
            std::size_t delay;
            std::size_t lastMovement;
        };

        AI _thisAI;

        inline const AI &findAI(const AIType &type) { return _aiVector.at(type); }

        static const std::unordered_map<AIType, AI> _aiVector;
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
