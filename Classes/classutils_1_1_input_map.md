---
title: utils::InputMap
summary: Bidirectional map between sf::Keyboard::Key and std::string. 

---

# utils::InputMap



Bidirectional map between sf::Keyboard::Key and std::string.  [More...](#detailed-description)

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[InputMap](Classes/classutils_1_1_input_map.md#function-inputmap)**(std::size_t keySize, std::size_t offset) |
| void | **[insert](Classes/classutils_1_1_input_map.md#function-insert)**(T t, const std::string & str) |
| const std::string & | **[at](Classes/classutils_1_1_input_map.md#function-at)**(T t) const |
| T | **[at](Classes/classutils_1_1_input_map.md#function-at)**(const std::string & string) const |

## Detailed Description

```cpp
template <typename T >
class utils::InputMap;
```

Bidirectional map between sf::Keyboard::Key and std::string. 
## Public Functions Documentation

### function InputMap

```cpp
inline explicit InputMap(
    std::size_t keySize,
    std::size_t offset
)
```


### function insert

```cpp
inline void insert(
    T t,
    const std::string & str
)
```


### function at

```cpp
inline const std::string & at(
    T t
) const
```


**Exceptions**: 

  * **std::out_of_range** if string is not in the map 


### function at

```cpp
inline T at(
    const std::string & string
) const
```


**Exceptions**: 

  * **std::out_of_range** if string is not in the map 


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100