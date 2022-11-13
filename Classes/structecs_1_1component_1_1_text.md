---
title: ecs::component::Text

---

# ecs::component::Text






`#include <Text.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Text](Classes/structecs_1_1component_1_1_text.md#function-text)**(size_t marginRight =0, const std::string & key ="nasa") |
| | **[Text](Classes/structecs_1_1component_1_1_text.md#function-text)**(const std::string & s1 ="", const std::string & s2 ="", const std::string & s3 ="", const std::string & s4 ="", const std::string & key ="nasa") |
| std::string | **[getContent](Classes/structecs_1_1component_1_1_text.md#function-getcontent)**(size_t pos) const |
| void | **[setContent](Classes/structecs_1_1component_1_1_text.md#function-setcontent)**(size_t pos, const std::string & newContent) |
| void | **[addContent](Classes/structecs_1_1component_1_1_text.md#function-addcontent)**(std::string & content) |
| void | **[clearContent](Classes/structecs_1_1component_1_1_text.md#function-clearcontent)**() |
| size_t | **[getContentSize](Classes/structecs_1_1component_1_1_text.md#function-getcontentsize)**() const |
| void | **[setTextColor](Classes/structecs_1_1component_1_1_text.md#function-settextcolor)**(short r, short g, short b, short a) |
| struct [textColor](Classes/structecs_1_1component_1_1text_color.md) | **[getTextColor](Classes/structecs_1_1component_1_1_text.md#function-gettextcolor)**() const |
| void | **[setFontKey](Classes/structecs_1_1component_1_1_text.md#function-setfontkey)**(const std::string & fontKey) |
| const sf::Font & | **[getFont](Classes/structecs_1_1component_1_1_text.md#function-getfont)**() const |
| void | **[setMarginRight](Classes/structecs_1_1component_1_1_text.md#function-setmarginright)**(size_t marginRight) |
| size_t | **[getMarginRight](Classes/structecs_1_1component_1_1_text.md#function-getmarginright)**() const |

## Public Functions Documentation

### function Text

```cpp
inline Text(
    size_t marginRight =0,
    const std::string & key ="nasa"
)
```


### function Text

```cpp
inline Text(
    const std::string & s1 ="",
    const std::string & s2 ="",
    const std::string & s3 ="",
    const std::string & s4 ="",
    const std::string & key ="nasa"
)
```


### function getContent

```cpp
inline std::string getContent(
    size_t pos
) const
```


### function setContent

```cpp
inline void setContent(
    size_t pos,
    const std::string & newContent
)
```


### function addContent

```cpp
inline void addContent(
    std::string & content
)
```


### function clearContent

```cpp
inline void clearContent()
```


### function getContentSize

```cpp
inline size_t getContentSize() const
```


### function setTextColor

```cpp
inline void setTextColor(
    short r,
    short g,
    short b,
    short a
)
```


### function getTextColor

```cpp
inline struct textColor getTextColor() const
```


### function setFontKey

```cpp
inline void setFontKey(
    const std::string & fontKey
)
```


### function getFont

```cpp
inline const sf::Font & getFont() const
```


### function setMarginRight

```cpp
inline void setMarginRight(
    size_t marginRight
)
```


### function getMarginRight

```cpp
inline size_t getMarginRight() const
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100