---
title: ecs::Entity

---

# ecs::Entity






`#include <Entity.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[operator size_t &](Classes/classecs_1_1_entity.md#function-operator-size-t-&)**() |
| | **[operator size_t](Classes/classecs_1_1_entity.md#function-operator-size-t)**() const |

## Friends

|                | Name           |
| -------------- | -------------- |
| class | **[Registry](Classes/classecs_1_1_entity.md#friend-registry)**  |

## Public Functions Documentation

### function operator size_t &

```cpp
inline explicit operator size_t &()
```


**Return**: Private member _id of the [Entity](Classes/classecs_1_1_entity.md)

Operators for the [Entity](Classes/classecs_1_1_entity.md) class used to get the Id of the entity 


### function operator size_t

```cpp
inline explicit operator size_t() const
```


## Friends

### friend Registry

```cpp
friend class Registry(
    Registry 
);
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100