---
title: ecs::component::MovementAI
summary: MovementAI component. 

---

# ecs::component::MovementAI



[MovementAI]() component. 


`#include <MovementAI.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| enum| **[AIType](Classes/structecs_1_1component_1_1_movement_a_i.md#enum-aitype)** { Idle, QuickUpDown, LongUpDown, QuickLeftRight, LongLeftRight, ClockwiseSmall, ClockwiseBig, AntiClockwiseSmall, AntiClockwiseBig}<br>All possible AI created.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[MovementAI](Classes/structecs_1_1component_1_1_movement_a_i.md#function-movementai)**(const [AIType](Classes/structecs_1_1component_1_1_movement_a_i.md#enum-aitype) & type =[Idle](Classes/structecs_1_1component_1_1_movement_a_i.md#enumvalue-idle))<br>[MovementAI](Classes/structecs_1_1component_1_1_movement_a_i.md) constructor.  |
| const std::pair< char, char > & | **[getNextDirection](Classes/structecs_1_1component_1_1_movement_a_i.md#function-getnextdirection)**()<br>get the next direction of the entity and cycles through the directions vector  |
| const std::size_t & | **[getDelay](Classes/structecs_1_1component_1_1_movement_a_i.md#function-getdelay)**() const<br>Get the Delay between each AI steps.  |
| const std::size_t & | **[getLastMovement](Classes/structecs_1_1component_1_1_movement_a_i.md#function-getlastmovement)**() const<br>Get the last time the AI entity has moved.  |
| void | **[setLastMovement](Classes/structecs_1_1component_1_1_movement_a_i.md#function-setlastmovement)**(const std::size_t & lastMovement)<br>Set the last time the AI entity has moved.  |

## Public Types Documentation

### enum AIType

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| Idle | |   |
| QuickUpDown | |   |
| LongUpDown | |   |
| QuickLeftRight | |   |
| LongLeftRight | |   |
| ClockwiseSmall | |   |
| ClockwiseBig | |   |
| AntiClockwiseSmall | |   |
| AntiClockwiseBig | |   |



All possible AI created. 

**Warning**: ALL MUST BE CREATED IN [MovementAI.cpp](Files/_movement_a_i_8cpp.md#file-movementai.cpp)

## Public Functions Documentation

### function MovementAI

```cpp
inline MovementAI(
    const AIType & type =Idle
)
```

[MovementAI](Classes/structecs_1_1component_1_1_movement_a_i.md) constructor. 

**Parameters**: 

  * **type** the AIType of the entity 


### function getNextDirection

```cpp
inline const std::pair< char, char > & getNextDirection()
```

get the next direction of the entity and cycles through the directions vector 

**Return**: the next direction of the entity as a std::pair of chars 

### function getDelay

```cpp
inline const std::size_t & getDelay() const
```

Get the Delay between each AI steps. 

**Return**: the delay in seconds 

### function getLastMovement

```cpp
inline const std::size_t & getLastMovement() const
```

Get the last time the AI entity has moved. 

**Return**: the last time the AI has moved 

### function setLastMovement

```cpp
inline void setLastMovement(
    const std::size_t & lastMovement
)
```

Set the last time the AI entity has moved. 

**Parameters**: 

  * **lastMovement** the last time the AI has moved 


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100