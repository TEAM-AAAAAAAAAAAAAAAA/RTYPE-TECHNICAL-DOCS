---
title: ecs::component::Drawable

---

# ecs::component::Drawable



 [More...](#detailed-description)


`#include <Drawable.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Drawable](Classes/structecs_1_1component_1_1_drawable.md#function-drawable)**(const std::string & key, float rotation =0.0)<br>Construct a new [Drawable](Classes/structecs_1_1component_1_1_drawable.md) object with the full texture.  |
| | **[Drawable](Classes/structecs_1_1component_1_1_drawable.md#function-drawable)**(const std::string & key, sf::IntRect rect, float rotation =0.0)<br>Construct a new [Drawable](Classes/structecs_1_1component_1_1_drawable.md) object.  |
| sf::Texture & | **[getTexture](Classes/structecs_1_1component_1_1_drawable.md#function-gettexture)**() |
| const sf::Texture & | **[getTexture](Classes/structecs_1_1component_1_1_drawable.md#function-gettexture)**() const |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| std::string | **[textureKey](Classes/structecs_1_1component_1_1_drawable.md#variable-texturekey)**  |
| sf::IntRect | **[rect](Classes/structecs_1_1component_1_1_drawable.md#variable-rect)**  |
| float | **[rotation](Classes/structecs_1_1component_1_1_drawable.md#variable-rotation)**  |

## Detailed Description

```cpp
struct ecs::component::Drawable;
```


[Drawable](Classes/structecs_1_1component_1_1_drawable.md) component is used to know if the [Entity](Classes/classecs_1_1_entity.md) is able to be draw and in which manner It differs by constructor parameters 

## Public Functions Documentation

### function Drawable

```cpp
inline Drawable(
    const std::string & key,
    float rotation =0.0
)
```

Construct a new [Drawable](Classes/structecs_1_1component_1_1_drawable.md) object with the full texture. 

**Parameters**: 

  * **texture** the texture key 


### function Drawable

```cpp
inline Drawable(
    const std::string & key,
    sf::IntRect rect,
    float rotation =0.0
)
```

Construct a new [Drawable](Classes/structecs_1_1component_1_1_drawable.md) object. 

**Parameters**: 

  * **texture** the texture key 
  * **rect** the rect to use from the texture 


### function getTexture

```cpp
inline sf::Texture & getTexture()
```


### function getTexture

```cpp
inline const sf::Texture & getTexture() const
```


## Public Attributes Documentation

### variable textureKey

```cpp
std::string textureKey;
```


### variable rect

```cpp
sf::IntRect rect;
```


### variable rotation

```cpp
float rotation;
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100