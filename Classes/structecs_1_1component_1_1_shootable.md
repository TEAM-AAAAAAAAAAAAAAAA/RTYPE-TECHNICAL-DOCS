---
title: ecs::component::Shootable

---

# ecs::component::Shootable



 [More...](#detailed-description)


`#include <Shootable.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Shootable](Classes/structecs_1_1component_1_1_shootable.md#function-shootable)**(sf::Keyboard::Key shoot, sf::Keyboard::Key shootSecondary =sf::Keyboard::Key::Unknown) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| sf::Keyboard::Key | **[Shoot](Classes/structecs_1_1component_1_1_shootable.md#variable-shoot)**  |
| sf::Keyboard::Key | **[ShootSecondary](Classes/structecs_1_1component_1_1_shootable.md#variable-shootsecondary)**  |

## Detailed Description

```cpp
struct ecs::component::Shootable;
```


[Shootable](Classes/structecs_1_1component_1_1_shootable.md) component define if the entity is able to shoot on other entities. In brief if it can damage another one 

## Public Functions Documentation

### function Shootable

```cpp
inline explicit Shootable(
    sf::Keyboard::Key shoot,
    sf::Keyboard::Key shootSecondary =sf::Keyboard::Key::Unknown
)
```


**Parameters**: 

  * **shoot** Primary shoot sfml key 
  * **shootSecondary** Secondary shoot sfml key, unknown as default 


Default constructor of the component, 


## Public Attributes Documentation

### variable Shoot

```cpp
sf::Keyboard::Key Shoot;
```


### variable ShootSecondary

```cpp
sf::Keyboard::Key ShootSecondary;
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100