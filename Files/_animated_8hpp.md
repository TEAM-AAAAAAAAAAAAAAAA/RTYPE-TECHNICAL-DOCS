---
title: src/ecs/components/client/Animated.hpp

---

# src/ecs/components/client/Animated.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::Animated](Classes/structecs_1_1component_1_1_animated.md)**  |
| struct | **[ecs::component::Animated::AnimFrame](Classes/structecs_1_1component_1_1_animated_1_1_anim_frame.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** Animated
*/

#pragma once

#include <vector>
#include "SFML/Graphics.hpp"

namespace ecs::component
{
    struct Animated {
        struct AnimFrame {
            AnimFrame(int x, int y, int width, int height, int delay)
                : x(x), y(y), width(width), height(height), delay(delay)
            {
            }
            int x;
            int y;
            int width;
            int height;
            int delay;
        };

        Animated(const AnimFrame &frame) : _currentFrame(0), lastSwitch(0) { _loadFrames(frame); }

        template <class... Frames> Animated(const AnimFrame &first, Frames... frames) : _currentFrame(0), lastSwitch(0)
        {
            _loadFrames(first, frames...);
        }

        int64_t lastSwitch;

        AnimFrame getFrame()
        {
            return _animFrames[_currentFrame];
        }

        const AnimFrame getFrame() const { return _animFrames[_currentFrame]; }

        sf::IntRect getFrameRect()
        {
            return sf::IntRect(_animFrames[_currentFrame].x, _animFrames[_currentFrame].y,
                _animFrames[_currentFrame].width, _animFrames[_currentFrame].height);
        }

        const sf::IntRect getFrameRect() const
        {
            return sf::IntRect(_animFrames[_currentFrame].x, _animFrames[_currentFrame].y,
                _animFrames[_currentFrame].width, _animFrames[_currentFrame].height);
        }

        void nextFrame()
        {
            if (_currentFrame < _animFrames.size() - 1)
                _currentFrame++;
            else
                _currentFrame = 0;
        }

      private:
        void _loadFrames() {}
        void _loadFrames(AnimFrame first)
        {
            _animFrames.push_back(first);
        }
        template <class... Frames> void _loadFrames(AnimFrame first, Frames... next)
        {
            _animFrames.push_back(first);
            _loadFrames(next...);
        }

        int _currentFrame;
        std::vector<AnimFrame> _animFrames;
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100
