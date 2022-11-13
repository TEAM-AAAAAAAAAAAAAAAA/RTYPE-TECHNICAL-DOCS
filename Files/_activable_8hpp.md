---
title: src/ecs/components/client/Activable.hpp

---

# src/ecs/components/client/Activable.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::Activable](Classes/structecs_1_1component_1_1_activable.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, by hourcadettej on 11/11/22.
** rtype
** File description:
** rtype
*/

#pragma once
#include "Constant.hpp"

namespace ecs::component
{
    struct Activable {

        Activable(bool isActivate = true, bool isButton = false, utils::constant::ButtonType buttonType = utils::constant::UNDEFINED) : _isActivate(isActivate), _isButton(isButton), _buttonType(buttonType), _isHover(false){}

        inline void setIsActivate(bool isActivate) { _isActivate = isActivate;};
        inline bool getIsActivate() const {return _isActivate;};
        inline void setIsButton(bool isButton) {_isButton = isButton;};
        inline bool getIsButton() const {return _isButton;};
        inline void setIsHover(bool isHover) {_isHover = isHover;};
        inline bool getIsHover() const {return _isHover;};
        inline void setButtonType(utils::constant::ButtonType buttonType) {_buttonType = buttonType;};
        inline utils::constant::ButtonType getButtonType() {return _buttonType;};
        inline void switchSetIsActivate() {_isActivate = !_isActivate;};

      private:
        bool _isActivate;
        bool _isButton;
        bool _isHover;
        utils::constant::ButtonType _buttonType;
    };
} // namespace ecs::component
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100
