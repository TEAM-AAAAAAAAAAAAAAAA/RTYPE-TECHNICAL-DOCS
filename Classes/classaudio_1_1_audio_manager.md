---
title: audio::AudioManager

---

# audio::AudioManager



 [More...](#detailed-description)


`#include <AudioManager.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[~AudioManager](Classes/classaudio_1_1_audio_manager.md#function-~audiomanager)**() =default |
| bool | **[loadBGM](Classes/classaudio_1_1_audio_manager.md#function-loadbgm)**(const std::string & key)<br>load a background music to be played  |
| bool | **[playBGM](Classes/classaudio_1_1_audio_manager.md#function-playbgm)**(bool loop =true) |
| bool | **[stopBGM](Classes/classaudio_1_1_audio_manager.md#function-stopbgm)**() |
| bool | **[setBGMVolume](Classes/classaudio_1_1_audio_manager.md#function-setbgmvolume)**(float volume) |
| float | **[getBGMVolume](Classes/classaudio_1_1_audio_manager.md#function-getbgmvolume)**() |
| sf::SoundSource::Status | **[getBGMStatus](Classes/classaudio_1_1_audio_manager.md#function-getbgmstatus)**() |
| void | **[loopBGM](Classes/classaudio_1_1_audio_manager.md#function-loopbgm)**(bool loop) |
| void | **[loadSFX](Classes/classaudio_1_1_audio_manager.md#function-loadsfx)**(const std::string & key)<br>load a sound effect to be played  |
| void | **[playSFX](Classes/classaudio_1_1_audio_manager.md#function-playsfx)**(const std::string & key) |
| void | **[setSFXVolume](Classes/classaudio_1_1_audio_manager.md#function-setsfxvolume)**(float volume) |
| float | **[getSFXVolume](Classes/classaudio_1_1_audio_manager.md#function-getsfxvolume)**() |

## Detailed Description

```cpp
class audio::AudioManager;
```


This class manages all the sounds and musics of the game Basic operations on background musics and sound effects are supported 

## Public Functions Documentation

### function ~AudioManager

```cpp
~AudioManager() =default
```


### function loadBGM

```cpp
static bool loadBGM(
    const std::string & key
)
```

load a background music to be played 

**Parameters**: 

  * **key** the key relative to the AssetLoader 


**Return**: true if the music was loaded 

### function playBGM

```cpp
static bool playBGM(
    bool loop =true
)
```


**Parameters**: 

  * **loop** if the music should loop, defaulted to true 
  * **volume** the volume of the music, defaulted to 100 


**Return**: true if the music is playing, false otherwise 

play the current background music 


### function stopBGM

```cpp
static bool stopBGM()
```


**Return**: true if the music is stopped, false otherwise 

stop the current background music 


### function setBGMVolume

```cpp
static bool setBGMVolume(
    float volume
)
```


**Parameters**: 

  * **volume0** = min, 100 = max 


**Return**: true if the volume is set, false otherwise 

Set the background music volume 


### function getBGMVolume

```cpp
static float getBGMVolume()
```


### function getBGMStatus

```cpp
static sf::SoundSource::Status getBGMStatus()
```


### function loopBGM

```cpp
static void loopBGM(
    bool loop
)
```


**Parameters**: 

  * **loop** true to play in loop, false to play once 


Set whether or not the stream should loop after reaching the end. 


### function loadSFX

```cpp
static void loadSFX(
    const std::string & key
)
```

load a sound effect to be played 

**Parameters**: 

  * **key** the key relative to the AssetLoader 


**Warning**: Do not use, this is for development only 

### function playSFX

```cpp
static void playSFX(
    const std::string & key
)
```


### function setSFXVolume

```cpp
static void setSFXVolume(
    float volume
)
```


**Parameters**: 

  * **volume0** = min, 100 = max 


**Return**: true if the volume is set, false otherwise 

Set the sound effects volume 


### function getSFXVolume

```cpp
static float getSFXVolume()
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100