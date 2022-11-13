---
title: src/client/Animation.hpp

---

# src/client/Animation.hpp



## Namespaces

| Name           |
| -------------- |
| **[anim](Namespaces/namespaceanim.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[anim::Animation](Classes/classanim_1_1_animation.md)** <br>[Animation]() class should be used to create an animation in sfml.  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** R-TYPE
** File description:
** Animation
*/

#pragma once

#include <SFML/Graphics.hpp>

namespace anim {
    class Animation {
        public:
            Animation();

            ~Animation() = default;

            void update();

            void addTexture(const std::string &texturePath, const sf::Vector2f &position, const sf::Vector2f &size);

            void addTexture(const sf::Image &image, const sf::Vector2f &position, const sf::Vector2f &size);

            const sf::RectangleShape &getShape() const;

            void moveShape(const sf::Vector2f &move);

            void setDuration(const std::size_t &duration);

            const std::size_t &getDuration() const;

            void setPosition(const sf::Vector2f &position);

            const sf::Vector2f &getPosition() const;

            void setSize(const sf::Vector2f &size);

            const sf::Vector2f &getSize() const;

            const sf::FloatRect getGlobalBounds();

            void setColor(const sf::Color &color);

            const sf::Color &getColor() const;

        private:
            sf::RectangleShape _shape;

            std::vector<sf::Texture> _textures;

            sf::Clock _clock;

            std::size_t _duration;

            std::size_t _textureUsed;
    };
} // namespace gui
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
