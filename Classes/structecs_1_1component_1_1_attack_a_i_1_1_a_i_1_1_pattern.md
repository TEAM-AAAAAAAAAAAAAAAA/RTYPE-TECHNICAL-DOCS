---
title: ecs::component::AttackAI::AI::Pattern
summary: The Pattern structure contains a std::functions and a reloadTime. Patterns are created in the CPP file. 

---

# ecs::component::AttackAI::AI::Pattern



The [Pattern]() structure contains a std::functions and a reloadTime. Patterns are created in the CPP file. 


`#include <AttackAI.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Pattern](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i_1_1_pattern.md#function-pattern)**(short reloadTime, std::function< void(const std::size_t)> pattern)<br>Construct a new [Pattern](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i_1_1_pattern.md) object.  |
| void | **[run](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i_1_1_pattern.md#function-run)**(const std::size_t & shooter) const<br>Run the pattern's function.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| short | **[reloadTime](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i_1_1_pattern.md#variable-reloadtime)**  |
| std::function< void(const std::size_t)> | **[_function](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i_1_1_pattern.md#variable--function)**  |

## Public Functions Documentation

### function Pattern

```cpp
inline Pattern(
    short reloadTime,
    std::function< void(const std::size_t)> pattern
)
```

Construct a new [Pattern](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i_1_1_pattern.md) object. 

**Parameters**: 

  * **reloadTime** the time the entity will have to wait before using another pattern again after this one 
  * **pattern** the function to call when this pattern is selected to be used by the [AI](Classes/structecs_1_1component_1_1_attack_a_i_1_1_a_i.md)


### function run

```cpp
inline void run(
    const std::size_t & shooter
) const
```

Run the pattern's function. 

**Parameters**: 

  * **shooter** which entity triggered the action 


## Public Attributes Documentation

### variable reloadTime

```cpp
short reloadTime;
```


### variable _function

```cpp
std::function< void(const std::size_t)> _function;
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100