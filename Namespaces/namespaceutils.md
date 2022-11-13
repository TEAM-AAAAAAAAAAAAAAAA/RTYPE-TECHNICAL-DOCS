---
title: utils

---

# utils



## Namespaces

| Name           |
| -------------- |
| **[utils::constant](Namespaces/namespaceutils_1_1constant.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[utils::InputMap](Classes/classutils_1_1_input_map.md)** <br>Bidirectional map between sf::Keyboard::Key and std::string.  |
| class | **[utils::Window](Classes/classutils_1_1_window.md)**  |

## Functions

|                | Name           |
| -------------- | -------------- |
| template <typename T \> <br>[InputMap](Classes/classutils_1_1_input_map.md)< T > & | **[getInstance](Namespaces/namespaceutils.md#function-getinstance)**() |
| std::string | **[toString](Modules/group___input.md#function-tostring)**(sf::Keyboard::Key key) |
| sf::Keyboard::Key | **[toKey](Modules/group___input.md#function-tokey)**(std::string string) |

## Attributes

|                | Name           |
| -------------- | -------------- |
| [InputMap](Classes/classutils_1_1_input_map.md)< sf::Keyboard::Key >(sf::Keyboard::Key) | **[initMap](Namespaces/namespaceutils.md#variable-initmap)**  |


## Functions Documentation

### function getInstance

```cpp
template <typename T >
InputMap< T > & getInstance()
```


### function toString

```cpp
std::string toString(
    sf::Keyboard::Key key
)
```


**Exceptions**: 

  * **std::out_of_range** if _key_ is not a valid key 


Returns the string associated with the _key_

The returned string is identical to the enum identifier. For example: 

```cpp
utils::toString(sf::Keyboard::A) == "A"
```


### function toKey

```cpp
sf::Keyboard::Key toKey(
    std::string string
)
```


**Parameters**: 

  * **string** 


**Exceptions**: 

  * **std::out_of_range** if _string_ is not a valid key 


Return the key interpretation of _string_

The passed string must be identical to the enum identifier. For example: 

```cpp
utils::toKey("A") == sf::Keyboard::A
```



## Attributes Documentation

### variable initMap

```cpp
InputMap< sf::Keyboard::Key >(sf::Keyboard::Key) initMap;
```





-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100