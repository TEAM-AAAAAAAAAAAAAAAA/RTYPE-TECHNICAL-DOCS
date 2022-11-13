---
title: ecs::component::Controllable

---

# ecs::component::Controllable



 [More...](#detailed-description)


`#include <Controllable.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Controllable](Classes/structecs_1_1component_1_1_controllable.md#function-controllable)**(sf::Keyboard::Key moveUp, sf::Keyboard::Key moveLeft, sf::Keyboard::Key moveDown, sf::Keyboard::Key moveRight, sf::Keyboard::Key hitBox, sf::Keyboard::Key moveUpSecondary =sf::Keyboard::Unknown, sf::Keyboard::Key moveLeftSecondary =sf::Keyboard::Unknown, sf::Keyboard::Key moveDownSecondary =sf::Keyboard::Unknown, sf::Keyboard::Key moveRightSecondary =sf::Keyboard::Unknown) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| sf::Keyboard::Key | **[MoveUp](Classes/structecs_1_1component_1_1_controllable.md#variable-moveup)**  |
| sf::Keyboard::Key | **[MoveLeft](Classes/structecs_1_1component_1_1_controllable.md#variable-moveleft)**  |
| sf::Keyboard::Key | **[MoveDown](Classes/structecs_1_1component_1_1_controllable.md#variable-movedown)**  |
| sf::Keyboard::Key | **[MoveRight](Classes/structecs_1_1component_1_1_controllable.md#variable-moveright)**  |
| sf::Keyboard::Key | **[MoveUpSecondary](Classes/structecs_1_1component_1_1_controllable.md#variable-moveupsecondary)**  |
| sf::Keyboard::Key | **[MoveLeftSecondary](Classes/structecs_1_1component_1_1_controllable.md#variable-moveleftsecondary)**  |
| sf::Keyboard::Key | **[MoveDownSecondary](Classes/structecs_1_1component_1_1_controllable.md#variable-movedownsecondary)**  |
| sf::Keyboard::Key | **[MoveRightSecondary](Classes/structecs_1_1component_1_1_controllable.md#variable-moverightsecondary)**  |
| sf::Keyboard::Key | **[HitBox](Classes/structecs_1_1component_1_1_controllable.md#variable-hitbox)**  |

## Detailed Description

```cpp
struct ecs::component::Controllable;
```


[Controllable](Classes/structecs_1_1component_1_1_controllable.md) component represents all the authorized input for the user In brief, it currently manage the following inputs : Up, Down, Right, Left Secondary Up, Secondary Down, Secondary Left, Secondary Right, 

## Public Functions Documentation

### function Controllable

```cpp
inline Controllable(
    sf::Keyboard::Key moveUp,
    sf::Keyboard::Key moveLeft,
    sf::Keyboard::Key moveDown,
    sf::Keyboard::Key moveRight,
    sf::Keyboard::Key hitBox,
    sf::Keyboard::Key moveUpSecondary =sf::Keyboard::Unknown,
    sf::Keyboard::Key moveLeftSecondary =sf::Keyboard::Unknown,
    sf::Keyboard::Key moveDownSecondary =sf::Keyboard::Unknown,
    sf::Keyboard::Key moveRightSecondary =sf::Keyboard::Unknown
)
```


## Public Attributes Documentation

### variable MoveUp

```cpp
sf::Keyboard::Key MoveUp;
```


### variable MoveLeft

```cpp
sf::Keyboard::Key MoveLeft;
```


### variable MoveDown

```cpp
sf::Keyboard::Key MoveDown;
```


### variable MoveRight

```cpp
sf::Keyboard::Key MoveRight;
```


### variable MoveUpSecondary

```cpp
sf::Keyboard::Key MoveUpSecondary;
```


### variable MoveLeftSecondary

```cpp
sf::Keyboard::Key MoveLeftSecondary;
```


### variable MoveDownSecondary

```cpp
sf::Keyboard::Key MoveDownSecondary;
```


### variable MoveRightSecondary

```cpp
sf::Keyboard::Key MoveRightSecondary;
```


### variable HitBox

```cpp
sf::Keyboard::Key HitBox;
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100