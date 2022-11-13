---
title: src/ecs/components/client/Drawable.hpp

---

# src/ecs/components/client/Drawable.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::Drawable](Classes/structecs_1_1component_1_1_drawable.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** Drawable
*/

#pragma once

#include "../../../client/AssetLoader.hpp"
#include "SFML/Graphics/Texture.hpp"

namespace ecs::component
{
    struct Drawable {
        Drawable(const std::string &key, float rotation = 0.0) : textureKey(key), rotation(rotation)
        {
            sf::Vector2u size = asset::AssetLoader::GetTexture(key).getSize();
            rect = {0, 0, static_cast<int>(size.x), static_cast<int>(size.y)};
        }

        Drawable(const std::string &key, sf::IntRect rect, float rotation = 0.0)
            : rect(rect), textureKey(key), rotation(rotation) {}

        inline sf::Texture &getTexture() { return asset::AssetLoader::GetTexture(textureKey); }

        inline const sf::Texture &getTexture() const { return asset::AssetLoader::GetTexture(textureKey); }

        std::string textureKey;
        sf::IntRect rect;
        float rotation;
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
