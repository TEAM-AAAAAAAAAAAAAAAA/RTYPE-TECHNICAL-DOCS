---
title: src/ecs/Registry.hpp

---

# src/ecs/Registry.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[ecs::Registry](Classes/classecs_1_1_registry.md)**  |




## Source code

```cpp
#pragma once

#include <any>
#include <exception>
#include <functional>
#include <iostream>
#include <map>
#include <typeindex>
#include "Constant.hpp"
#include "Entity.hpp"
#include "SparseArray.hpp"

namespace ecs
{
    class Registry {
      public:
        Registry() : _lastEntity(0) {}

        template <class Component> SparseArray<Component> &registerComponent()
        {
            if (_componentsArrays.find(std::type_index(typeid(Component))) != _componentsArrays.end())
                return getComponents<Component>();
            _componentsArrays[std::type_index(typeid(Component))] = SparseArray<Component>();

            std::function<void(Registry &, Entity const &)> erase_func = [](Registry &r, Entity const &e) {
                SparseArray<Component> &array = r.getComponents<Component>();
                if (e._id > array.size())
                    return;
                array.erase(e._id);
            };
            _eraseFunctions.push_back(erase_func);
            return getComponents<Component>();
        }

        template <class Component> SparseArray<Component> &getComponents()
        {
            return std::any_cast<SparseArray<Component> &>(_componentsArrays.at(std::type_index(typeid(Component))));
        }

        template <class Component> SparseArray<Component> const &getComponents() const
        {
            return std::any_cast<SparseArray<Component>>(_componentsArrays.at(std::type_index(typeid(Component))));
        }

        Entity spawn_entity()
        {
            size_t front;

            if (_entitiesBin.empty()) {
                _lastEntity++;
                return Entity(_lastEntity - 1);
            }
            front = _entitiesBin.front();
            _entitiesBin.erase(_entitiesBin.begin());
            return Entity(front);
        }

        Entity entityFromIndex(std::size_t idx)
        {
            if (idx >= _lastEntity) {
                std::cerr << "Error with entity " << idx << "(" << _lastEntity << " max)" << std::endl;
            }
            return Entity(idx);
        }

        void killEntity(Entity const &e)
        {
            if (e._id == utils::constant::npos)
                return;
            for (const auto &eraseFunc : _eraseFunctions)
                eraseFunc(*this, e);
            _entitiesBin.push_back(e._id);
        }

        template <typename Component>
        typename SparseArray<Component>::referenceType addComponent(Entity const &to, Component &&c)
        {
            return std::any_cast<SparseArray<Component> &>(_componentsArrays[std::type_index(typeid(Component))])
                .insertAt(to._id, c);
        }

        template <typename Component, typename... Params>
        typename SparseArray<Component>::referenceType emplaceComponent(Entity const &to, Params &&...p)
        {
            return std::any_cast<SparseArray<Component> &>(_componentsArrays[std::type_index(typeid(Component))])
                .emplaceAt(to._id, p...);
        }
        template <typename Component> void removeComponent(Entity const &from)
        {
            std::any_cast<SparseArray<Component> &>(_componentsArrays.at(std::type_index(typeid(Component))))[from] =
                std::nullopt;
        }

      private:
        std::map<std::type_index, std::any> _componentsArrays;

        std::vector<std::function<void(Registry &, Entity const &)>> _eraseFunctions;

        std::vector<std::size_t> _entitiesBin;

        std::size_t _lastEntity;
    };
} // namespace ecs
```


-------------------------------

Updated on 2022-11-13 at 16:52:00 +0100
