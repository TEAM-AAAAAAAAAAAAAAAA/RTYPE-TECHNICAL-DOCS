---
title: src/utils/Window.hpp

---

# src/utils/Window.hpp



## Namespaces

| Name           |
| -------------- |
| **[utils](Namespaces/namespaceutils.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[utils::Window](Classes/classutils_1_1_window.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** Window
*/

#pragma once

#ifdef CLIENT_COMPILATION_MODE
    #include "Constant.hpp"
    #include <SFML/Graphics.hpp>

namespace utils
{
    class Window {
      public:
        Window() {}
        ~Window() {}
        static sf::Color Color;
        static inline bool isOpen() { return getInstance().isOpen(); }

        static sf::RenderWindow &getInstance()
        {
            static sf::RenderWindow instance(
                sf::RenderWindow(sf::VideoMode(utils::constant::mapWidth, utils::constant::mapHeight), "r-type"));
            return instance;
        }
    };
} // namespace utils
#else
namespace utils
{
    class Window {
      public:
        ~Window() {}
        static inline bool isOpen() { return true; }
    };
} // namespace utils
#endif
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
