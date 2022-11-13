---
title: anim::Animation
summary: Animation class should be used to create an animation in sfml. 

---

# anim::Animation



[Animation]() class should be used to create an animation in sfml.  [More...](#detailed-description)


`#include <Animation.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Animation](Classes/classanim_1_1_animation.md#function-animation)**()<br>Create a new instance of [Animation](Classes/classanim_1_1_animation.md).  |
| | **[~Animation](Classes/classanim_1_1_animation.md#function-~animation)**() =default<br>Destroy the instance of [Animation](Classes/classanim_1_1_animation.md). It's set to default.  |
| void | **[update](Classes/classanim_1_1_animation.md#function-update)**()<br>It updates the texture used depending on the duration time and the previous index in the vector of texture.  |
| void | **[addTexture](Classes/classanim_1_1_animation.md#function-addtexture)**(const std::string & texturePath, const sf::Vector2f & position, const sf::Vector2f & size)<br>It adds a texture on the vector of texture used for the animation.  |
| void | **[addTexture](Classes/classanim_1_1_animation.md#function-addtexture)**(const sf::Image & image, const sf::Vector2f & position, const sf::Vector2f & size)<br>It adds a texture on the vector of texture used for the animation.  |
| const sf::RectangleShape & | **[getShape](Classes/classanim_1_1_animation.md#function-getshape)**() const<br>It returns the shape of the animation with the correct texture.  |
| void | **[moveShape](Classes/classanim_1_1_animation.md#function-moveshape)**(const sf::Vector2f & move)<br>It move the shape of the animation with the vector2f move.  |
| void | **[setDuration](Classes/classanim_1_1_animation.md#function-setduration)**(const std::size_t & duration)<br>It sets the duration between each frame of the animation.  |
| const std::size_t & | **[getDuration](Classes/classanim_1_1_animation.md#function-getduration)**() const<br>It gets the duration between each frame of the animation.  |
| void | **[setPosition](Classes/classanim_1_1_animation.md#function-setposition)**(const sf::Vector2f & position)<br>It sets the position of the shape used for the animation.  |
| const sf::Vector2f & | **[getPosition](Classes/classanim_1_1_animation.md#function-getposition)**() const<br>It gets the position of the shape used for the animation.  |
| void | **[setSize](Classes/classanim_1_1_animation.md#function-setsize)**(const sf::Vector2f & size)<br>It sets the size of the shape used for the animation.  |
| const sf::Vector2f & | **[getSize](Classes/classanim_1_1_animation.md#function-getsize)**() const<br>It gets the size of the shape used for the animation.  |
| const sf::FloatRect | **[getGlobalBounds](Classes/classanim_1_1_animation.md#function-getglobalbounds)**()<br>It gets the size of the shape used for the animation.  |
| void | **[setColor](Classes/classanim_1_1_animation.md#function-setcolor)**(const sf::Color & color)<br>It sets the color of the shape used for the animation.  |
| const sf::Color & | **[getColor](Classes/classanim_1_1_animation.md#function-getcolor)**() const<br>It gets the color of the shape used for the animation.  |

## Detailed Description

```cpp
class anim::Animation;
```

[Animation]() class should be used to create an animation in sfml. 

**Note**: It contains a vector of texture that will be updated, depending on a duration time, with the function update. You should define a duration between each frame. You should define a position for the animation. You should define a size for the animation. You should add a texture for the animation. 

**Warning**: A texture is always add at the end of the vector of texture. 
## Public Functions Documentation

### function Animation

```cpp
Animation()
```

Create a new instance of [Animation](Classes/classanim_1_1_animation.md). 

### function ~Animation

```cpp
~Animation() =default
```

Destroy the instance of [Animation](Classes/classanim_1_1_animation.md). It's set to default. 

### function update

```cpp
void update()
```

It updates the texture used depending on the duration time and the previous index in the vector of texture. 

### function addTexture

```cpp
void addTexture(
    const std::string & texturePath,
    const sf::Vector2f & position,
    const sf::Vector2f & size
)
```

It adds a texture on the vector of texture used for the animation. 

**Parameters**: 

  * **texturePath** The path to load the texture from. 
  * **position** The position from which the texture of the loaded image is to be obtained. 
  * **size** The size to get the texture from in the image loaded. 


**Exceptions**: 

  * **AnimationException** will be thrown if the image cannot be loaded. 


**Warning**: Be carful, the texture is added at the end of the vector. Please add texture in the correct order. 

### function addTexture

```cpp
void addTexture(
    const sf::Image & image,
    const sf::Vector2f & position,
    const sf::Vector2f & size
)
```

It adds a texture on the vector of texture used for the animation. 

**Parameters**: 

  * **image** The image used to create the texture from. 
  * **position** The position from which the texture of the loaded image is to be obtained. 
  * **size** The size to get the texture from in the image loaded. 


**Exceptions**: 

  * **AnimationException** will be thrown if the texture cannot be created. 


**Warning**: Be carful, the texture is added at the end of the vector. Please add texture in the correct order. 

### function getShape

```cpp
const sf::RectangleShape & getShape() const
```

It returns the shape of the animation with the correct texture. 

**Return**: const sf::RectangleShape reference of the shape. 

**Note**: Use this function to get the shape to be drawn. 

**Warning**: Keep in mind that you need to update the texture with the `update` function. 

### function moveShape

```cpp
void moveShape(
    const sf::Vector2f & move
)
```

It move the shape of the animation with the vector2f move. 

**Note**: Use this function to move the shape. 

**Warning**: Keep in mind that you need to draw the shape again. 

### function setDuration

```cpp
void setDuration(
    const std::size_t & duration
)
```

It sets the duration between each frame of the animation. 

**Parameters**: 

  * **duration** The duration between each frame of the animation as millisecond. 


**Note**: The animation must be set as millisecond. 

### function getDuration

```cpp
const std::size_t & getDuration() const
```

It gets the duration between each frame of the animation. 

**Return**: const std::size_t reference of the duration. 

### function setPosition

```cpp
void setPosition(
    const sf::Vector2f & position
)
```

It sets the position of the shape used for the animation. 

**Parameters**: 

  * **position** The position to be set on the shape. 


### function getPosition

```cpp
const sf::Vector2f & getPosition() const
```

It gets the position of the shape used for the animation. 

**Return**: const sf::Vector2f reference of the position. 

### function setSize

```cpp
void setSize(
    const sf::Vector2f & size
)
```

It sets the size of the shape used for the animation. 

**Parameters**: 

  * **size** The size to be set on the shape. 


### function getSize

```cpp
const sf::Vector2f & getSize() const
```

It gets the size of the shape used for the animation. 

**Return**: const sf::Vector2f reference of the size. 

### function getGlobalBounds

```cpp
const sf::FloatRect getGlobalBounds()
```

It gets the size of the shape used for the animation. 

**Return**: const sf::Vector2f reference of the size. 

### function setColor

```cpp
void setColor(
    const sf::Color & color
)
```

It sets the color of the shape used for the animation. 

**Parameters**: 

  * **color** The color to be set on the shape. 


### function getColor

```cpp
const sf::Color & getColor() const
```

It gets the color of the shape used for the animation. 

**Return**: const sf::Color reference of the size. 

-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100