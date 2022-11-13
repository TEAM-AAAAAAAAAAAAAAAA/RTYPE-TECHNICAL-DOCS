---
title: src/ecs/Event.hpp

---

# src/ecs/Event.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[ecs::Event](Classes/classecs_1_1_event.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** Event
*/

#pragma once

namespace ecs
{
    class Event {
      public:
        enum EventType {
            Null,
            Unknown,
            Quit,
            Move,
            MoveUp,
            MoveLeft,
            MoveDown,
            MoveRight,
            MoveStop,
            HitBox,
            Shoot,
            UIUp,
            UILeft,
            UIDown,
            UIRight,
            UIEnter,
        };
        Event() = delete;

        Event(EventType e) : _e(e) {}

        inline bool operator==(const Event other) const
        {
            if (_e == other._e)
                return true;
            return false;
        }

        inline bool operator==(const Event::EventType type) const
        {
            if (_e == type)
                return true;
            return false;
        }

        inline bool operator!=(const Event other) const { return _e != other._e; };

        inline bool operator!=(const Event::EventType type) const { return _e != type; };

        inline char serialize() const { return _e; }

      private:
        const EventType _e;
    };
} // namespace ecs
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
