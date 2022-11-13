---
title: ecs::component::Direction

---

# ecs::component::Direction



 [More...](#detailed-description)


`#include <Direction.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Direction](Classes/structecs_1_1component_1_1_direction.md#function-direction)**(char x, char y, bool hasMoved =false) |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| char | **[x](Classes/structecs_1_1component_1_1_direction.md#variable-x)**  |
| char | **[y](Classes/structecs_1_1component_1_1_direction.md#variable-y)**  |
| bool | **[hasMoved](Classes/structecs_1_1component_1_1_direction.md#variable-hasmoved)**  |

## Detailed Description

```cpp
struct ecs::component::Direction;
```


[Direction](Classes/structecs_1_1component_1_1_direction.md) component is used to know where the entity is moving x represents the x-axis (horizontally) y represents the y-axis (vertically) hasMoved is used to know if the entity changed its direction since the last synchronisation with the server 

## Public Functions Documentation

### function Direction

```cpp
inline Direction(
    char x,
    char y,
    bool hasMoved =false
)
```


## Public Attributes Documentation

### variable x

```cpp
char x;
```


### variable y

```cpp
char y;
```


### variable hasMoved

```cpp
bool hasMoved;
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100