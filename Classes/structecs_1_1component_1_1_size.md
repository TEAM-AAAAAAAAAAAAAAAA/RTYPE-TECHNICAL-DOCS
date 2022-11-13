---
title: ecs::component::Size
summary: Size component. 

---

# ecs::component::Size



[Size]() component. 


`#include <Size.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| std::array< char, 4 > | **[serialize](Classes/structecs_1_1component_1_1_size.md#function-serialize)**()<br>serialize the component  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| int | **[height](Classes/structecs_1_1component_1_1_size.md#variable-height)**  |
| int | **[width](Classes/structecs_1_1component_1_1_size.md#variable-width)**  |

## Public Functions Documentation

### function serialize

```cpp
inline std::array< char, 4 > serialize()
```

serialize the component 

**Return**: the serialized component 

## Public Attributes Documentation

### variable height

```cpp
int height;
```


### variable width

```cpp
int width;
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100