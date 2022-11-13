---
title: asset::AssetLoader

---

# asset::AssetLoader



 [More...](#detailed-description)


`#include <AssetLoader.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[~AssetLoader](Classes/classasset_1_1_asset_loader.md#function-~assetloader)**() =default |
| template <class... Args\> <br>void | **[LoadTexture](Classes/classasset_1_1_asset_loader.md#function-loadtexture)**(const std::string & key, const std::filesystem::path & path, std::string_view next, Args... args)<br>load an SFML asset and add it to the map  |
| void | **[LoadTexture](Classes/classasset_1_1_asset_loader.md#function-loadtexture)**(const std::string & key, std::vector< std::string > paths) |
| template <class... Args\> <br>void | **[LoadBGM](Classes/classasset_1_1_asset_loader.md#function-loadbgm)**(const std::string & key, const std::filesystem::path & path, std::string_view next, Args... args)<br>Load a background music and add it to the map.  |
| void | **[LoadBGM](Classes/classasset_1_1_asset_loader.md#function-loadbgm)**(const std::string & key, std::vector< std::string > paths) |
| template <class... Args\> <br>void | **[LoadSFX](Classes/classasset_1_1_asset_loader.md#function-loadsfx)**(const std::string & key, const std::filesystem::path & path, std::string_view next, Args... args)<br>Load a sound effect and add it to the map.  |
| void | **[LoadSFX](Classes/classasset_1_1_asset_loader.md#function-loadsfx)**(const std::string & key, std::vector< std::string > paths) |
| template <class... Args\> <br>void | **[LoadFont](Classes/classasset_1_1_asset_loader.md#function-loadfont)**(const std::string & key, const std::filesystem::path & path, std::string_view next, Args... args)<br>load a font and add it to the map  |
| void | **[LoadFont](Classes/classasset_1_1_asset_loader.md#function-loadfont)**(const std::string & key, std::vector< std::string > paths) |
| void | **[loadKeybind](Classes/classasset_1_1_asset_loader.md#function-loadkeybind)**(const std::string & action, const std::string & key) |
| std::filesystem::path | **[smartPath](Classes/classasset_1_1_asset_loader.md#function-smartpath)**(std::vector< std::string > paths)<br>create a smartpath from a vector of string  |
| sf::Texture & | **[GetTexture](Classes/classasset_1_1_asset_loader.md#function-gettexture)**(const std::string & key)<br>Get an Asset object from the map.  |
| sf::Music & | **[GetBGM](Classes/classasset_1_1_asset_loader.md#function-getbgm)**(const std::string & key)<br>Get a background music object from the map.  |
| sf::Sound & | **[GetSFX](Classes/classasset_1_1_asset_loader.md#function-getsfx)**(const std::string & key)<br>Get a sound effect object from the map.  |
| sf::Font & | **[GetFont](Classes/classasset_1_1_asset_loader.md#function-getfont)**(const std::string & key)<br>Get a font object from the mapb.  |
| sf::Keyboard::Key & | **[GetKeybind](Classes/classasset_1_1_asset_loader.md#function-getkeybind)**(const std::string & key) |
| void | **[LoadIniFile](Classes/classasset_1_1_asset_loader.md#function-loadinifile)**(const std::filesystem::path & path)<br>Load a .ini file with boost loading assets into the map.  |
| [AssetLoader](Classes/classasset_1_1_asset_loader.md) & | **[getInstance](Classes/classasset_1_1_asset_loader.md#function-getinstance)**() |
| std::filesystem::path | **[smartPath](Classes/classasset_1_1_asset_loader.md#function-smartpath)**(std::filesystem::path path) |
| template <class... Args\> <br>std::filesystem::path | **[smartPath](Classes/classasset_1_1_asset_loader.md#function-smartpath)**(std::filesystem::path path, std::string_view next, Args... args) |
| void | **[display_key_from_map](Classes/classasset_1_1_asset_loader.md#function-display-key-from-map)**() |

## Detailed Description

```cpp
class asset::AssetLoader;
```


This class loads all the assets neened by the game and stores them in a map Basic operatations on assets are supported An asset is either a texture, a sound or a font 

## Public Functions Documentation

### function ~AssetLoader

```cpp
~AssetLoader() =default
```


Destroy the [AssetLoader](Classes/classasset_1_1_asset_loader.md) object 


### function LoadTexture

```cpp
template <class... Args>
static inline void LoadTexture(
    const std::string & key,
    const std::filesystem::path & path,
    std::string_view next,
    Args... args
)
```

load an SFML asset and add it to the map 

**Parameters**: 

  * **key** the key to load the asset 
  * **path** first segment of the path of the asset 
  * **next** next segment of the path of the asset 
  * **args** other segments of the path 


### function LoadTexture

```cpp
static inline void LoadTexture(
    const std::string & key,
    std::vector< std::string > paths
)
```


### function LoadBGM

```cpp
template <class... Args>
static inline void LoadBGM(
    const std::string & key,
    const std::filesystem::path & path,
    std::string_view next,
    Args... args
)
```

Load a background music and add it to the map. 

**Parameters**: 

  * **key** the key to load the asset 
  * **path** first segment of the path of the asset 
  * **next** next segment of the path of the asset 
  * **args** other segments of the path 


**Template Parameters**: 

  * **Args** Path segments 


### function LoadBGM

```cpp
static inline void LoadBGM(
    const std::string & key,
    std::vector< std::string > paths
)
```


### function LoadSFX

```cpp
template <class... Args>
static inline void LoadSFX(
    const std::string & key,
    const std::filesystem::path & path,
    std::string_view next,
    Args... args
)
```

Load a sound effect and add it to the map. 

**Parameters**: 

  * **key** the key to load the asset 
  * **path** first segment of the path of the asset 
  * **next** next segment of the path of the asset 
  * **args** other segments of the path 


**Template Parameters**: 

  * **Args** Path segments 


### function LoadSFX

```cpp
static inline void LoadSFX(
    const std::string & key,
    std::vector< std::string > paths
)
```


### function LoadFont

```cpp
template <class... Args>
static inline void LoadFont(
    const std::string & key,
    const std::filesystem::path & path,
    std::string_view next,
    Args... args
)
```

load a font and add it to the map 

**Parameters**: 

  * **key** the key to load the font 
  * **path** first segment of the path of the font 
  * **next** next segment of the path of the font 
  * **args** other segments of the path 


### function LoadFont

```cpp
static inline void LoadFont(
    const std::string & key,
    std::vector< std::string > paths
)
```


### function loadKeybind

```cpp
static inline void loadKeybind(
    const std::string & action,
    const std::string & key
)
```


### function smartPath

```cpp
static inline std::filesystem::path smartPath(
    std::vector< std::string > paths
)
```

create a smartpath from a vector of string 

### function GetTexture

```cpp
static inline sf::Texture & GetTexture(
    const std::string & key
)
```

Get an Asset object from the map. 

**Parameters**: 

  * **key** of the asset to get 


**Return**: sf::Texture& the texture 

### function GetBGM

```cpp
static inline sf::Music & GetBGM(
    const std::string & key
)
```

Get a background music object from the map. 

**Parameters**: 

  * **key** of the asset to get 


**Return**: sf::Music& the music 

### function GetSFX

```cpp
static inline sf::Sound & GetSFX(
    const std::string & key
)
```

Get a sound effect object from the map. 

**Parameters**: 

  * **key** of the asset to get 


**Return**: sf::Sound& the sound effect 

### function GetFont

```cpp
static inline sf::Font & GetFont(
    const std::string & key
)
```

Get a font object from the mapb. 

**Parameters**: 

  * **key** of the asset to get 


**Return**: sf::Font& the font 

### function GetKeybind

```cpp
static inline sf::Keyboard::Key & GetKeybind(
    const std::string & key
)
```


### function LoadIniFile

```cpp
static inline void LoadIniFile(
    const std::filesystem::path & path
)
```

Load a .ini file with boost loading assets into the map. 

### function getInstance

```cpp
static AssetLoader & getInstance()
```


the instance of the [AssetLoader](Classes/classasset_1_1_asset_loader.md) object 


### function smartPath

```cpp
static inline std::filesystem::path smartPath(
    std::filesystem::path path
)
```


### function smartPath

```cpp
template <class... Args>
static inline std::filesystem::path smartPath(
    std::filesystem::path path,
    std::string_view next,
    Args... args
)
```


### function display_key_from_map

```cpp
static inline void display_key_from_map()
```


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100