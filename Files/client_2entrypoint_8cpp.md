---
title: src/client/entrypoint.cpp

---

# src/client/entrypoint.cpp



## Functions

|                | Name           |
| -------------- | -------------- |
| int | **[main](Files/client_2entrypoint_8cpp.md#function-main)**() |


## Functions Documentation

### function main

```cpp
int main()
```


**Return**: 0 if no error, anything otherwise 

Main function of the client, running everything to start the game 




## Source code

```cpp
/*
** EPITECH PROJECT, by hourcadettej on 10/3/22.
** rtype
** File description:
** rtype
*/

#include "AssetLoader.hpp"
#include "AudioManager.hpp"
#include "Engine.hpp"
#include "GetWorld.hpp"
#include "LockedQueue.hpp"
#include "NetworkClient.hpp"

int main()
{
    ecs::Engine engine;
//    network::Message msg;
//    msg.fill(0);
//    network::Client::connect();
//    network::Client::getOutgoingMessages().push(msg);
    asset::AssetLoader::LoadIniFile(asset::AssetLoader::smartPath("assets", "config.ini"));
    audio::AudioManager::playSFX("splash_screen");
    ecs::WorldManager::setWaitingWorld(getMenuWorld);
    audio::AudioManager::setBGMVolume(50);
    audio::AudioManager::setSFXVolume(50);
    engine.run();
    return 0;
}
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
