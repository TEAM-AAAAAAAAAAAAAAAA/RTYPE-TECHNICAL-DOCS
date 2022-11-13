---
title: ecs::component::AttackAI
summary: AttackAI component. 

---

# ecs::component::AttackAI



[AttackAI]() component. 


`#include <AttackAI.hpp>`

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Action](Classes/structecs_1_1component_1_1_attack_a_i_1_1_action.md)** <br>The [Action]() structure contains the prototypes of the functions used by patterns.  |
| struct | **[AI](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i.md)** <br>The [AI]() structure where the pattern of the entity is defined.  |

## Public Types

|                | Name           |
| -------------- | -------------- |
| enum| **[AIType](Classes/structecs_1_1component_1_1_attack_a_i.md#enum-aitype)** { None, Battlecruiser, Dreadnought, Fighter, Frigate, Scout, Torpedo, NoodleMonster, PlayerBot}<br>All possible [AI]() created.  |
| enum| **[PatternType](Classes/structecs_1_1component_1_1_attack_a_i.md#enum-patterntype)** { Wait, WaitShort, WaitLong, ShootBullet, ShootEnergySphere, ShootEnergySphereFast, ShootLaser, ShootRocket, InvokeAllies, InvokeAnyone, SpawnAsteroids, PlayerBotLaser}<br>All possible Patterns created.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[AttackAI](Classes/structecs_1_1component_1_1_attack_a_i.md#function-attackai)**(const [AIType](Classes/structecs_1_1component_1_1_attack_a_i.md#enum-aitype) & type =[None](Classes/structecs_1_1component_1_1_attack_a_i.md#enumvalue-none))<br>[AttackAI](Classes/structecs_1_1component_1_1_attack_a_i.md) constructor.  |
| const [AttackAI::AI::Pattern](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i_1_1_pattern.md) & | **[getRandomAttack](Classes/structecs_1_1component_1_1_attack_a_i.md#function-getrandomattack)**() const<br>Get a random attack from the [AI]().  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| size_t | **[lastAttack](Classes/structecs_1_1component_1_1_attack_a_i.md#variable-lastattack)**  |
| size_t | **[lastAttackDelay](Classes/structecs_1_1component_1_1_attack_a_i.md#variable-lastattackdelay)**  |

## Public Types Documentation

### enum AIType

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| None | |   |
| Battlecruiser | |   |
| Dreadnought | |   |
| Fighter | |   |
| Frigate | |   |
| Scout | |   |
| Torpedo | |   |
| NoodleMonster | |   |
| PlayerBot | |   |



All possible [AI]() created. 

**Warning**: ALL MUST BE CREATED IN [AttackAI.cpp](Files/_attack_a_i_8cpp.md#file-attackai.cpp)

### enum PatternType

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| Wait | |   |
| WaitShort | |   |
| WaitLong | |   |
| ShootBullet | |   |
| ShootEnergySphere | |   |
| ShootEnergySphereFast | |   |
| ShootLaser | |   |
| ShootRocket | |   |
| InvokeAllies | |   |
| InvokeAnyone | |   |
| SpawnAsteroids | |   |
| PlayerBotLaser | |   |



All possible Patterns created. 

**Warning**: ALL MUST BE CREATED IN [AttackAI.cpp](Files/_attack_a_i_8cpp.md#file-attackai.cpp)

## Public Functions Documentation

### function AttackAI

```cpp
inline AttackAI(
    const AIType & type =None
)
```

[AttackAI](Classes/structecs_1_1component_1_1_attack_a_i.md) constructor. 

**Parameters**: 

  * **type** the AIType of the entity 


### function getRandomAttack

```cpp
inline const AttackAI::AI::Pattern & getRandomAttack() const
```

Get a random attack from the [AI](). 

## Public Attributes Documentation

### variable lastAttack

```cpp
size_t lastAttack;
```


### variable lastAttackDelay

```cpp
size_t lastAttackDelay;
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100