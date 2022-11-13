---
title: ecs::component::NetworkId
summary: NetworkId component related to the entity sent to the client. 

---

# ecs::component::NetworkId



[NetworkId]() component related to the entity sent to the client. 


`#include <NetworkId.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[NetworkId](Classes/structecs_1_1component_1_1_network_id.md#function-networkid)**() |
| | **[NetworkId](Classes/structecs_1_1component_1_1_network_id.md#function-networkid)**(size_t id) |
| std::array< char, 2 > | **[serialize](Classes/structecs_1_1component_1_1_network_id.md#function-serialize)**()<br>Serialize the component.  |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| size_t | **[id](Classes/structecs_1_1component_1_1_network_id.md#variable-id)**  |

## Public Functions Documentation

### function NetworkId

```cpp
inline NetworkId()
```


### function NetworkId

```cpp
inline NetworkId(
    size_t id
)
```


### function serialize

```cpp
inline std::array< char, 2 > serialize()
```

Serialize the component. 

**Return**: The serialized component 

## Public Attributes Documentation

### variable id

```cpp
size_t id;
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100