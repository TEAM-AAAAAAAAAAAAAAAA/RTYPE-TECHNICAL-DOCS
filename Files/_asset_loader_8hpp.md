---
title: src/client/AssetLoader.hpp

---

# src/client/AssetLoader.hpp



## Namespaces

| Name           |
| -------------- |
| **[asset](Namespaces/namespaceasset.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[asset::AssetLoader](Classes/classasset_1_1_asset_loader.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** R-TYPEMIRROR
** File description:
** AssetLoader
*/

#pragma once

#include <SFML/Audio.hpp>
#include <SFML/Graphics.hpp>
#include <filesystem>
#include <iostream>
#include <memory>
#include <optional>
#include <string>
#include <boost/property_tree/ini_parser.hpp>
#include <boost/property_tree/ptree.hpp>
#include <unordered_map>
#include <utility>
#include "InputMap.hpp"

namespace asset
{
    class AssetLoader {
      public:
        ~AssetLoader() = default;

        template <class... Args>
        static void LoadTexture(
            const std::string &key, const std::filesystem::path &path, std::string_view next, Args... args)
        {
            sf::Texture texture;

            std::filesystem::path smart = smartPath(path, next, args...);

            if (!texture.loadFromFile(smart.generic_string()))
                return;
            getInstance()._textureMap[key] = texture;
        }

        static void LoadTexture(const std::string &key, std::vector<std::string> paths)
        {
            sf::Texture texture;

            std::filesystem::path smart = smartPath(std::move(paths));

            if (!texture.loadFromFile(smart.generic_string()))
                return;
            getInstance()._textureMap[key] = texture;
        }

        template <class... Args>
        static void LoadBGM(
            const std::string &key, const std::filesystem::path &path, std::string_view next, Args... args)
        {
            std::filesystem::path smart = smartPath(path, next, args...);

            if (!getInstance()._bgmMap[key].openFromFile(smart.generic_string()))
                return;
        }

        static void LoadBGM(const std::string &key, std::vector<std::string> paths)
        {
            std::filesystem::path smart = smartPath(std::move(paths));

            if (!getInstance()._bgmMap[key].openFromFile(smart.generic_string()))
                return;
        }

        template <class... Args>
        static void LoadSFX(
            const std::string &key, const std::filesystem::path &path, std::string_view next, Args... args)
        {
            std::filesystem::path smart = smartPath(path, next, args...);

            if (!getInstance()._sfxBufferMap[key].loadFromFile(smart.generic_string()))
                return;
            getInstance()._sfxMap[key].setBuffer(getInstance()._sfxBufferMap[key]);
        }

        static void LoadSFX(const std::string &key, std::vector<std::string> paths)
        {
            std::filesystem::path smart = smartPath(std::move(paths));

            if (!getInstance()._sfxBufferMap[key].loadFromFile(smart.generic_string()))
                return;
            getInstance()._sfxMap[key].setBuffer(getInstance()._sfxBufferMap[key]);
        }

        template <class... Args>
        static void LoadFont(
            const std::string &key, const std::filesystem::path &path, std::string_view next, Args... args)
        {
            sf::Font font;

            std::filesystem::path smart = smartPath(path, next, args...);

            if (!font.loadFromFile(smart.generic_string()))
                return;
            getInstance()._fontMap[key] = font;
        }

        static void LoadFont(const std::string &key, std::vector<std::string> paths)
        {
            sf::Font font;

            std::filesystem::path smart = smartPath(std::move(paths));

            if (!font.loadFromFile(smart.generic_string()))
                return;
            getInstance()._fontMap[key] = font;
        }

        static void loadKeybind(const std::string &action, const std::string &key)
        {
            getInstance()._keyMap[action] = utils::toKey(key);
        }

        static std::filesystem::path smartPath(std::vector<std::string> paths)
        {
            std::filesystem::path smart = paths[0];

            for (int i = 1; i < paths.size(); i++) {
                smart.append(paths[i]);
            }
            return smart;
        }

        static sf::Texture &GetTexture(const std::string &key) { return getInstance()._textureMap[key]; }

        static sf::Music &GetBGM(const std::string &key) { return getInstance()._bgmMap[key]; }

        static sf::Sound &GetSFX(const std::string &key) { return getInstance()._sfxMap[key]; }

        static sf::Font &GetFont(const std::string &key) { return getInstance()._fontMap[key]; }

        static sf::Keyboard::Key &GetKeybind(const std::string &key) { return getInstance()._keyMap[key]; }

        static void LoadIniFile(const std::filesystem::path &path)
        {
            boost::property_tree::ptree pt;
            try {
                boost::property_tree::ini_parser::read_ini(path.generic_string(), pt);
            } catch (std::exception &e) {
                std::cout << e.what() << std::endl;
            }

            // loop through the sections
            for (auto &section : pt) {
                for (auto &value : section.second) {
                    std::vector<std::string> paths;
                    // parse the section.second with slash and put it in the vector
                    while (value.second.data().find('/') != std::string::npos) {
                        paths.push_back(value.second.data().substr(0, value.second.data().find('/')));
                        value.second.data().erase(0, value.second.data().find('/') + 1);
                    }
                    if (section.first == "keybind") {
                        loadKeybind(value.first, value.second.data());
                        continue;
                    }
                    paths.push_back(value.second.data());

                    if (section.first == "texture")
                        LoadTexture(value.first, paths);
                    if (section.first == "bgm")
                        LoadBGM(value.first, paths);
                    if (section.first == "sfx")
                        LoadSFX(value.first, paths);
                    if (section.first == "font")
                        LoadFont(value.first, paths);
                }
            }
        }

        static AssetLoader &getInstance();

        static inline std::filesystem::path smartPath(std::filesystem::path path) { return path; }

        template <class... Args>
        static std::filesystem::path smartPath(std::filesystem::path path, std::string_view next, Args... args)
        {
            return smartPath(path.append(next), args...);
        }

        static void display_key_from_map()
        {
            std::cout << "len of map: " << getInstance()._textureMap.size() << std::endl;
            for (auto &key : getInstance()._textureMap) {
                std::cout << key.first << std::endl;
            }
        }

      private:
        std::unordered_map<std::string, sf::Texture> _textureMap;

        std::unordered_map<std::string, sf::Music> _bgmMap;

        std::unordered_map<std::string, sf::SoundBuffer> _sfxBufferMap;

        std::unordered_map<std::string, sf::Sound> _sfxMap;

        std::unordered_map<std::string, sf::Font> _fontMap;

        std::unordered_map<std::string, sf::Keyboard::Key> _keyMap;
    };
} // namespace asset
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100
