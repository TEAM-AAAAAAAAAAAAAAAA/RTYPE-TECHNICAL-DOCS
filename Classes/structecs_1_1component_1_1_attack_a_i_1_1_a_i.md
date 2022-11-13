---
title: ecs::component::AttackAI::AI
summary: The AI structure where the pattern of the entity is defined. 

---

# ecs::component::AttackAI::AI



The [AI]() structure where the pattern of the entity is defined. 


`#include <AttackAI.hpp>`

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[Pattern](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i_1_1_pattern.md)** <br>The [Pattern]() structure contains a std::functions and a reloadTime. Patterns are created in the CPP file.  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[AI](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i.md#function-ai)**(std::vector< [PatternType](Classes/structecs_1_1component_1_1_attack_a_i.md#enum-patterntype) > pattern)<br>Construct a new [AI](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i.md) object.  |
| | **[AI](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i.md#function-ai)**(const [AI](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i.md) & other)<br>[AI](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i.md) copy constructor.  |
| const std::vector< [PatternType](Classes/structecs_1_1component_1_1_attack_a_i.md#enum-patterntype) > & | **[getPatterns](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i.md#function-getpatterns)**() const<br>Get the Patterns of this [AI](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i.md).  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| const std::unordered_map< [PatternType](Classes/structecs_1_1component_1_1_attack_a_i.md#enum-patterntype), [Pattern](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i_1_1_pattern.md) > | **[patterns](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i.md#variable-patterns)**  |

## Public Functions Documentation

### function AI

```cpp
inline AI(
    std::vector< PatternType > pattern
)
```

Construct a new [AI](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i.md) object. 

**Parameters**: 

  * **direction** vector that takes pairs of chars 
  * **delay** the delay between each step 


### function AI

```cpp
inline AI(
    const AI & other
)
```

[AI](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i.md) copy constructor. 

**Parameters**: 

  * **other** another [AI](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i.md)


### function getPatterns

```cpp
inline const std::vector< PatternType > & getPatterns() const
```

Get the Patterns of this [AI](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i.md). 

**Return**: const std::vector<PatternType> 

## Public Attributes Documentation

### variable patterns

```cpp
static const std::unordered_map< PatternType, Pattern > patterns;
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100