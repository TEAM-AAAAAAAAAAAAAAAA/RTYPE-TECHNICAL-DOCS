---
title: src/utils/InputMap.hpp

---

# src/utils/InputMap.hpp



## Namespaces

| Name           |
| -------------- |
| **[utils](Namespaces/namespaceutils.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** rtype
** File description:
** InputMap
*/

#pragma once

#include <SFML/Window/Keyboard.hpp>
#include <string>

namespace utils {

    std::string toString(sf::Keyboard::Key key);

    sf::Keyboard::Key toKey(std::string string);

};
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
