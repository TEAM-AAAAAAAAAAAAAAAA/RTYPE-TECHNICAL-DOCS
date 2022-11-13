---
title: ecs::component::Hitbox

---

# ecs::component::Hitbox



 [More...](#detailed-description)


`#include <Hitbox.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Hitbox](Classes/structecs_1_1component_1_1_hitbox.md#function-hitbox)**() |
| void | **[switchHitBox](Classes/structecs_1_1component_1_1_hitbox.md#function-switchhitbox)**() |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| bool | **[enableHitBox](Classes/structecs_1_1component_1_1_hitbox.md#variable-enablehitbox)**  |

## Detailed Description

```cpp
struct ecs::component::Hitbox;
```


Used to show a red rectangle shape around the entity to display its hitBox 

## Public Functions Documentation

### function Hitbox

```cpp
inline explicit Hitbox()
```


### function switchHitBox

```cpp
inline void switchHitBox()
```


Used to switch the enable/disable mode of the hitBox pressing H 


## Public Attributes Documentation

### variable enableHitBox

```cpp
bool enableHitBox;
```


Toogle used to know if we need to enable or disable the HitBox 


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100