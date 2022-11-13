---
title: utils::constant

---

# utils::constant



## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[utils::constant::ButtonValue](Classes/structutils_1_1constant_1_1_button_value.md)**  |

## Types

|                | Name           |
| -------------- | -------------- |
| enum| **[PacketType](Namespaces/namespaceutils_1_1constant.md#enum-packettype)** { PLAYER_MOVE = 8, PLAYER_SHOT = 2, PLAYER_CHARGED_SHOT, PLAYER_POWERUP, ENTITY_MOVE, ENTITY_SPAWN, ENTITY_DEATH, ENTITY_DAMAGE, ENTITY_HEAL, NEW_WAVE, BOSS_STAGE, GAME_OVER, MULTIPLAYER_INFO, HEALTH_UPDATE, NONE} |
| enum| **[ButtonActionType](Namespaces/namespaceutils_1_1constant.md#enum-buttonactiontype)** { PLAY_ACTION, QUIT_ACTION, OPTIONS_ACTION, CONNECT_ACTION} |
| enum| **[ButtonType](Namespaces/namespaceutils_1_1constant.md#enum-buttontype)** { PLAY, OPTION, QUIT, PLAY_HOVER, OPTION_HOVER, QUIT_HOVER, ROOM, ROOM_HOVER, ROOM_TEXT, OPTION_INTERFACE, SOUND_LEFT, SOUND_RIGHT, SOUND_LEFT_HOVER, SOUND_RIGHT_HOVER, MUSIC_LEFT, MUSIC_RIGHT, MUSIC_RIGHT_HOVER, MUSIC_LEFT_HOVER, HOW_TO, HOW_TO_HOVER, SLIDE_MUSIC, SLIDE_SOUND, SOUND_BAR, SETTINGS, SETTINGS_HOVER, OPTIONS_TEXT, PLANET, UNDEFINED} |
| using std::chrono::high_resolution_clock | **[chrono](Namespaces/namespaceutils_1_1constant.md#using-chrono)**  |
| using std::chrono::duration< double, std::milli > | **[chronoDuration](Namespaces/namespaceutils_1_1constant.md#using-chronoduration)**  |

## Functions

|                | Name           |
| -------------- | -------------- |
| int | **[getPacketTypeKey](Namespaces/namespaceutils_1_1constant.md#function-getpackettypekey)**([PacketType](Namespaces/namespaceutils_1_1constant.md#enum-packettype) type) |

## Attributes

|                | Name           |
| -------------- | -------------- |
| const std::size_t | **[npos](Namespaces/namespaceutils_1_1constant.md#variable-npos)**  |
| short | **[mapWidth](Namespaces/namespaceutils_1_1constant.md#variable-mapwidth)**  |
| short | **[mapHeight](Namespaces/namespaceutils_1_1constant.md#variable-mapheight)**  |
| short | **[maxPlayerHealth](Namespaces/namespaceutils_1_1constant.md#variable-maxplayerhealth)**  |
| short | **[sizeHealthBar](Namespaces/namespaceutils_1_1constant.md#variable-sizehealthbar)**  |
| const std::map< [ButtonType](Namespaces/namespaceutils_1_1constant.md#enum-buttontype), [ButtonValue](Classes/structutils_1_1constant_1_1_button_value.md) > | **[buttonValueMap](Namespaces/namespaceutils_1_1constant.md#variable-buttonvaluemap)**  |
| std::map< int, [PacketType](Namespaces/namespaceutils_1_1constant.md#enum-packettype) > | **[mapPacketType](Namespaces/namespaceutils_1_1constant.md#variable-mappackettype)**  |

## Types Documentation

### enum PacketType

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| PLAYER_MOVE | 8|   |
| PLAYER_SHOT | 2|   |
| PLAYER_CHARGED_SHOT | |   |
| PLAYER_POWERUP | |   |
| ENTITY_MOVE | |   |
| ENTITY_SPAWN | |   |
| ENTITY_DEATH | |   |
| ENTITY_DAMAGE | |   |
| ENTITY_HEAL | |   |
| NEW_WAVE | |   |
| BOSS_STAGE | |   |
| GAME_OVER | |   |
| MULTIPLAYER_INFO | |   |
| HEALTH_UPDATE | |   |
| NONE | |   |




### enum ButtonActionType

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| PLAY_ACTION | |   |
| QUIT_ACTION | |   |
| OPTIONS_ACTION | |   |
| CONNECT_ACTION | |   |




### enum ButtonType

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| PLAY | |   |
| OPTION | |   |
| QUIT | |   |
| PLAY_HOVER | |   |
| OPTION_HOVER | |   |
| QUIT_HOVER | |   |
| ROOM | |   |
| ROOM_HOVER | |   |
| ROOM_TEXT | |   |
| OPTION_INTERFACE | |   |
| SOUND_LEFT | |   |
| SOUND_RIGHT | |   |
| SOUND_LEFT_HOVER | |   |
| SOUND_RIGHT_HOVER | |   |
| MUSIC_LEFT | |   |
| MUSIC_RIGHT | |   |
| MUSIC_RIGHT_HOVER | |   |
| MUSIC_LEFT_HOVER | |   |
| HOW_TO | |   |
| HOW_TO_HOVER | |   |
| SLIDE_MUSIC | |   |
| SLIDE_SOUND | |   |
| SOUND_BAR | |   |
| SETTINGS | |   |
| SETTINGS_HOVER | |   |
| OPTIONS_TEXT | |   |
| PLANET | |   |
| UNDEFINED | |   |




### using chrono

```cpp
using utils::constant::chrono = typedef std::chrono::high_resolution_clock;
```


### using chronoDuration

```cpp
using utils::constant::chronoDuration = typedef std::chrono::duration<double, std::milli>;
```



## Functions Documentation

### function getPacketTypeKey

```cpp
static int getPacketTypeKey(
    PacketType type
)
```



## Attributes Documentation

### variable npos

```cpp
static const std::size_t npos = -1;
```


### variable mapWidth

```cpp
static short mapWidth = 1920;
```


### variable mapHeight

```cpp
static short mapHeight = 1080;
```


### variable maxPlayerHealth

```cpp
static short maxPlayerHealth = 100;
```


### variable sizeHealthBar

```cpp
static short sizeHealthBar = 282;
```


### variable buttonValueMap

```cpp
static const std::map< ButtonType, ButtonValue > buttonValueMap {
            {PLAY, {324, 2079, 916, 292, 300, 100, 300, 280}},
            {OPTION, {3651, 2079, 916, 292, 300, 100, 300, 480}},
            {QUIT, {4760, 2079, 916, 292, 300, 100, 300, 680}},
            {PLAY_HOVER, {220, 2449, 1114, 356, 300, 100, 300, 280}},
            {OPTION_HOVER, {3542, 2456, 1114, 356, 300, 100, 300, 450}},
            {QUIT_HOVER, {4670, 2451, 1114, 356, 300, 100, 300, 620}},
            {ROOM, {326, 456, 1114, 356, 400, 100, 850, 250}},
            {OPTION_INTERFACE, {1692, 168, 1589, 1790, 692, 772, 800, 100}},
            {SOUND_LEFT, {3813, 178, 255, 256, 55, 55, 1260, 560}},
            {SOUND_RIGHT, {3489, 434, 255, 256, 55, 55, 1325, 560}},
            {SOUND_LEFT_HOVER, {3489, 178, 255, 256, 55, 55, 1260, 560}},
            {SOUND_RIGHT_HOVER, {3813, 434, 255, 256, 55, 55, 1325, 560}},
            {MUSIC_LEFT, {3813, 178, 255, 256, 55, 55, 1260, 360}},
            {MUSIC_RIGHT, {3489, 434, 255, 256, 55, 55, 1325, 360}},
            {MUSIC_LEFT_HOVER, {3489, 178, 255, 256, 55, 55, 1260, 360}},
            {MUSIC_RIGHT_HOVER, {3813, 434, 255, 256, 55, 55, 1325, 360}},
            {HOW_TO, {4137, 434, 255, 256, 55, 55, 1250, 700}},
            {HOW_TO_HOVER, {4137, 178, 255, 256, 55, 55, 1250, 700}},
            {SLIDE_SOUND, {4396, 1486, 97, 146, 21, 31, 1070, 572}},
            {SLIDE_MUSIC, {4396, 1486, 97, 146, 21, 31, 1070, 372}},
            {SOUND_BAR, {3476, 1692, 2213, 168, 350, 36, 900, 370}},
            {SETTINGS, {4461, 435, 255, 255, 55, 55, 970, 700}},
            {SETTINGS_HOVER, {4461, 178, 255, 255, 55, 55, 970, 700}},

        };
```


### variable mapPacketType

```cpp
static std::map< int, PacketType > mapPacketType {
            {1, PLAYER_MOVE},
            {2, PLAYER_SHOT},
            {4, PLAYER_CHARGED_SHOT},
            {8, ENTITY_MOVE},
            {16, ENTITY_SPAWN},
            {17, ENTITY_DEATH},
            {32, ENTITY_DAMAGE},
            {34, ENTITY_HEAL},
            {64, PLAYER_POWERUP},
            {3, NEW_WAVE},
            {7, BOSS_STAGE},
            {15, GAME_OVER},
            {31, MULTIPLAYER_INFO},
            {38, HEALTH_UPDATE}
        };
```





-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100