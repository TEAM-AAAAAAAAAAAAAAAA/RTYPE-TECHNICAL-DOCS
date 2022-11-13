---
title: ecs::component::Position

---

# ecs::component::Position






`#include <Position.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Position](Classes/structecs_1_1component_1_1_position.md#function-position)**(int x, int y) |
| std::array< char, 4 > | **[serialize](Classes/structecs_1_1component_1_1_position.md#function-serialize)**()<br>serialize the component  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| int | **[x](Classes/structecs_1_1component_1_1_position.md#variable-x)**  |
| int | **[y](Classes/structecs_1_1component_1_1_position.md#variable-y)**  |

## Public Functions Documentation

### function Position

```cpp
inline Position(
    int x,
    int y
)
```


### function serialize

```cpp
inline std::array< char, 4 > serialize()
```

serialize the component 

**Return**: the serialized component 

## Public Attributes Documentation

### variable x

```cpp
int x;
```


### variable y

```cpp
int y;
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100