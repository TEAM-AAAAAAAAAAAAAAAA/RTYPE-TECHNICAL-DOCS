---
title: ecs::Event

---

# ecs::Event



 [More...](#detailed-description)


`#include <Event.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| enum| **[EventType](Classes/classecs_1_1_event.md#enum-eventtype)** { Null, Unknown, Quit, Move, MoveUp, MoveLeft, MoveDown, MoveRight, MoveStop, HitBox, Shoot, UIUp, UILeft, UIDown, UIRight, UIEnter} |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Event](Classes/classecs_1_1_event.md#function-event)**() =delete |
| | **[Event](Classes/classecs_1_1_event.md#function-event)**([EventType](Classes/classecs_1_1_event.md#enum-eventtype) e) |
| bool | **[operator==](Classes/classecs_1_1_event.md#function-operator==)**(const [Event](Classes/classecs_1_1_event.md) other) const |
| bool | **[operator==](Classes/classecs_1_1_event.md#function-operator==)**(const [Event::EventType](Classes/classecs_1_1_event.md#enum-eventtype) type) const |
| bool | **[operator!=](Classes/classecs_1_1_event.md#function-operator!=)**(const [Event](Classes/classecs_1_1_event.md) other) const |
| bool | **[operator!=](Classes/classecs_1_1_event.md#function-operator!=)**(const [Event::EventType](Classes/classecs_1_1_event.md#enum-eventtype) type) const |
| char | **[serialize](Classes/classecs_1_1_event.md#function-serialize)**() const |

## Detailed Description

```cpp
class ecs::Event;
```


[Event](Classes/classecs_1_1_event.md) class is used to manage every events gave by the user The [Event](Classes/classecs_1_1_event.md) class make the link between the user and the back-end 

## Public Types Documentation

### enum EventType

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| Null | |   |
| Unknown | |   |
| Quit | |   |
| Move | |   |
| MoveUp | |   |
| MoveLeft | |   |
| MoveDown | |   |
| MoveRight | |   |
| MoveStop | |   |
| HitBox | |   |
| Shoot | |   |
| UIUp | |   |
| UILeft | |   |
| UIDown | |   |
| UIRight | |   |
| UIEnter | |   |




List every type of event currently managed 


## Public Functions Documentation

### function Event

```cpp
Event() =delete
```


Default constructor is deleted because you have to inform the event you want to treat 


### function Event

```cpp
inline Event(
    EventType e
)
```


**Parameters**: 

  * **e** The [Event](Classes/classecs_1_1_event.md) you want to treat 


Constructor of [Event](Classes/classecs_1_1_event.md) class 


### function operator==

```cpp
inline bool operator==(
    const Event other
) const
```


### function operator==

```cpp
inline bool operator==(
    const Event::EventType type
) const
```


### function operator!=

```cpp
inline bool operator!=(
    const Event other
) const
```


### function operator!=

```cpp
inline bool operator!=(
    const Event::EventType type
) const
```


### function serialize

```cpp
inline char serialize() const
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100