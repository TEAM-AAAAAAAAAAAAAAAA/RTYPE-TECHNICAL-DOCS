---
title: ecs::component::MovementAI::AI
summary: The AI structure where the pattern of the entity is defined. 

---

# ecs::component::MovementAI::AI



The AI structure where the pattern of the entity is defined. 

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[AI](Classes/structecs_1_1component_1_1_movement_a_i_1_1_a_i.md#function-ai)**(std::vector< std::pair< char, char > > direction, std::size_t delay)<br>Construct a new AI object.  |
| | **[AI](Classes/structecs_1_1component_1_1_movement_a_i_1_1_a_i.md#function-ai)**(const AI & other)<br>AI copy constructor.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| std::vector< std::pair< char, char > > | **[direction](Classes/structecs_1_1component_1_1_movement_a_i_1_1_a_i.md#variable-direction)**  |
| int | **[currentIndex](Classes/structecs_1_1component_1_1_movement_a_i_1_1_a_i.md#variable-currentindex)**  |
| std::size_t | **[delay](Classes/structecs_1_1component_1_1_movement_a_i_1_1_a_i.md#variable-delay)**  |
| std::size_t | **[lastMovement](Classes/structecs_1_1component_1_1_movement_a_i_1_1_a_i.md#variable-lastmovement)**  |

## Public Functions Documentation

### function AI

```cpp
inline AI(
    std::vector< std::pair< char, char > > direction,
    std::size_t delay
)
```

Construct a new AI object. 

**Parameters**: 

  * **direction** vector that takes pairs of chars 
  * **delay** the delay between each step 


### function AI

```cpp
inline AI(
    const AI & other
)
```

AI copy constructor. 

**Parameters**: 

  * **other** another AI 


## Public Attributes Documentation

### variable direction

```cpp
std::vector< std::pair< char, char > > direction;
```


### variable currentIndex

```cpp
int currentIndex;
```


### variable delay

```cpp
std::size_t delay;
```


### variable lastMovement

```cpp
std::size_t lastMovement;
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100