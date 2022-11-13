---
title: ecs::component::Activable

---

# ecs::component::Activable






`#include <Activable.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Activable](Classes/structecs_1_1component_1_1_activable.md#function-activable)**(bool isActivate =true, bool isButton =false, [utils::constant::ButtonType](Namespaces/namespaceutils_1_1constant.md#enum-buttontype) buttonType =[utils::constant::UNDEFINED](Namespaces/namespaceutils_1_1constant.md#enumvalue-undefined)) |
| void | **[setIsActivate](Classes/structecs_1_1component_1_1_activable.md#function-setisactivate)**(bool isActivate) |
| bool | **[getIsActivate](Classes/structecs_1_1component_1_1_activable.md#function-getisactivate)**() const |
| void | **[setIsButton](Classes/structecs_1_1component_1_1_activable.md#function-setisbutton)**(bool isButton) |
| bool | **[getIsButton](Classes/structecs_1_1component_1_1_activable.md#function-getisbutton)**() const |
| void | **[setIsHover](Classes/structecs_1_1component_1_1_activable.md#function-setishover)**(bool isHover) |
| bool | **[getIsHover](Classes/structecs_1_1component_1_1_activable.md#function-getishover)**() const |
| void | **[setButtonType](Classes/structecs_1_1component_1_1_activable.md#function-setbuttontype)**([utils::constant::ButtonType](Namespaces/namespaceutils_1_1constant.md#enum-buttontype) buttonType) |
| [utils::constant::ButtonType](Namespaces/namespaceutils_1_1constant.md#enum-buttontype) | **[getButtonType](Classes/structecs_1_1component_1_1_activable.md#function-getbuttontype)**() |
| void | **[switchSetIsActivate](Classes/structecs_1_1component_1_1_activable.md#function-switchsetisactivate)**() |

## Public Functions Documentation

### function Activable

```cpp
inline Activable(
    bool isActivate =true,
    bool isButton =false,
    utils::constant::ButtonType buttonType =utils::constant::UNDEFINED
)
```


### function setIsActivate

```cpp
inline void setIsActivate(
    bool isActivate
)
```


### function getIsActivate

```cpp
inline bool getIsActivate() const
```


### function setIsButton

```cpp
inline void setIsButton(
    bool isButton
)
```


### function getIsButton

```cpp
inline bool getIsButton() const
```


### function setIsHover

```cpp
inline void setIsHover(
    bool isHover
)
```


### function getIsHover

```cpp
inline bool getIsHover() const
```


### function setButtonType

```cpp
inline void setButtonType(
    utils::constant::ButtonType buttonType
)
```


### function getButtonType

```cpp
inline utils::constant::ButtonType getButtonType()
```


### function switchSetIsActivate

```cpp
inline void switchSetIsActivate()
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100