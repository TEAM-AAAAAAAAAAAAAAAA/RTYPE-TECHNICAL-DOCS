---
title: ecs::component::Weapon

---

# ecs::component::Weapon






`#include <Weapon.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Weapon](Classes/structecs_1_1component_1_1_weapon.md#function-weapon)**(int shootDelay, int damage, int projSpeed, std::pair< unsigned char, unsigned char > projSize, bool hasSuper =false, int superDamage =0, int superLoadingTime =0) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| int | **[shootDelay](Classes/structecs_1_1component_1_1_weapon.md#variable-shootdelay)**  |
| int | **[damage](Classes/structecs_1_1component_1_1_weapon.md#variable-damage)**  |
| int | **[projSpeed](Classes/structecs_1_1component_1_1_weapon.md#variable-projspeed)**  |
| std::pair< unsigned char, unsigned char > | **[projSize](Classes/structecs_1_1component_1_1_weapon.md#variable-projsize)**  |
| int64_t | **[lastShoot](Classes/structecs_1_1component_1_1_weapon.md#variable-lastshoot)**  |
| bool | **[hasSuper](Classes/structecs_1_1component_1_1_weapon.md#variable-hassuper)**  |
| int | **[superDamage](Classes/structecs_1_1component_1_1_weapon.md#variable-superdamage)**  |
| int | **[superLoadingTime](Classes/structecs_1_1component_1_1_weapon.md#variable-superloadingtime)**  |

## Public Functions Documentation

### function Weapon

```cpp
inline Weapon(
    int shootDelay,
    int damage,
    int projSpeed,
    std::pair< unsigned char, unsigned char > projSize,
    bool hasSuper =false,
    int superDamage =0,
    int superLoadingTime =0
)
```


## Public Attributes Documentation

### variable shootDelay

```cpp
int shootDelay;
```


### variable damage

```cpp
int damage;
```


### variable projSpeed

```cpp
int projSpeed;
```


### variable projSize

```cpp
std::pair< unsigned char, unsigned char > projSize;
```


### variable lastShoot

```cpp
int64_t lastShoot;
```


### variable hasSuper

```cpp
bool hasSuper;
```


### variable superDamage

```cpp
int superDamage;
```


### variable superLoadingTime

```cpp
int superLoadingTime;
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100