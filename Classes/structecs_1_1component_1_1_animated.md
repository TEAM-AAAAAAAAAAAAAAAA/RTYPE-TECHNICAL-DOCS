---
title: ecs::component::Animated

---

# ecs::component::Animated






`#include <Animated.hpp>`

## Public Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[AnimFrame](Classes/structecs_1_1component_1_1_animated_1_1_anim_frame.md)**  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Animated](Classes/structecs_1_1component_1_1_animated.md#function-animated)**(const [AnimFrame](Classes/structecs_1_1component_1_1_animated_1_1_anim_frame.md) & frame)<br>Construct a new [Animated](Classes/structecs_1_1component_1_1_animated.md) object with only one frame (replace [Drawable]()'s rect)  |
| template <class... Frames\> <br>| **[Animated](Classes/structecs_1_1component_1_1_animated.md#function-animated)**(const [AnimFrame](Classes/structecs_1_1component_1_1_animated_1_1_anim_frame.md) & first, Frames... frames)<br>Construct a new [Animated](Classes/structecs_1_1component_1_1_animated.md) object.  |
| [AnimFrame](Classes/structecs_1_1component_1_1_animated_1_1_anim_frame.md) | **[getFrame](Classes/structecs_1_1component_1_1_animated.md#function-getframe)**() |
| const [AnimFrame](Classes/structecs_1_1component_1_1_animated_1_1_anim_frame.md) | **[getFrame](Classes/structecs_1_1component_1_1_animated.md#function-getframe)**() const |
| sf::IntRect | **[getFrameRect](Classes/structecs_1_1component_1_1_animated.md#function-getframerect)**() |
| const sf::IntRect | **[getFrameRect](Classes/structecs_1_1component_1_1_animated.md#function-getframerect)**() const |
| void | **[nextFrame](Classes/structecs_1_1component_1_1_animated.md#function-nextframe)**() |

## Public Attributes

|                | Name           |
| -------------- | -------------- |
| int64_t | **[lastSwitch](Classes/structecs_1_1component_1_1_animated.md#variable-lastswitch)**  |

## Public Functions Documentation

### function Animated

```cpp
inline Animated(
    const AnimFrame & frame
)
```

Construct a new [Animated](Classes/structecs_1_1component_1_1_animated.md) object with only one frame (replace [Drawable]()'s rect) 

**Parameters**: 

  * **first** the only frame of the spritesheet 


### function Animated

```cpp
template <class... Frames>
inline Animated(
    const AnimFrame & first,
    Frames... frames
)
```

Construct a new [Animated](Classes/structecs_1_1component_1_1_animated.md) object. 

**Parameters**: 

  * **first** 
  * **frames** 


### function getFrame

```cpp
inline AnimFrame getFrame()
```


### function getFrame

```cpp
inline const AnimFrame getFrame() const
```


### function getFrameRect

```cpp
inline sf::IntRect getFrameRect()
```


### function getFrameRect

```cpp
inline const sf::IntRect getFrameRect() const
```


### function nextFrame

```cpp
inline void nextFrame()
```


## Public Attributes Documentation

### variable lastSwitch

```cpp
int64_t lastSwitch;
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100