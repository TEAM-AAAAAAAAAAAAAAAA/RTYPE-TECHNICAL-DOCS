---
title: src/client/AudioManager.hpp

---

# src/client/AudioManager.hpp



## Namespaces

| Name           |
| -------------- |
| **[audio](Namespaces/namespaceaudio.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[audio::AudioManager](Classes/classaudio_1_1_audio_manager.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** rtype
** File description:
** AudioManager
*/

#pragma once

#include <SFML/Audio.hpp>
#include <string>
#include <vector>

namespace audio
{

    class AudioManager {
      public:
        ~AudioManager() = default;

        static bool loadBGM(const std::string &key);

        static bool playBGM(bool loop = true);

        static bool stopBGM();

        static bool setBGMVolume(float volume);

        [[nodiscard]] static float getBGMVolume();

        [[nodiscard]] static sf::SoundSource::Status getBGMStatus();

        static void loopBGM(bool loop);

        static void loadSFX(const std::string &key);

        static void playSFX(const std::string &key);

        static void setSFXVolume(float volume);

        [[nodiscard]] static float getSFXVolume();

      private:
        AudioManager() = default;

        std::string _currentBGMKey;

        std::string _currentSFXKey;

        float _BGMVolume = 50.0f;

        float _SFXVolume = 50.0f;

        static AudioManager &getInstance();
    };
} // namespace audio
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
