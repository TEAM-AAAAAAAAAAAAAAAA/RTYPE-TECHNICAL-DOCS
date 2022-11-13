---
title: Input

---

# Input



## Functions

|                | Name           |
| -------------- | -------------- |
| std::string | **[toString](Modules/group___input.md#function-tostring)**(sf::Keyboard::Key key) |
| sf::Keyboard::Key | **[toKey](Modules/group___input.md#function-tokey)**(std::string string) |


## Functions Documentation

### function toString

```
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

```
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






-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100