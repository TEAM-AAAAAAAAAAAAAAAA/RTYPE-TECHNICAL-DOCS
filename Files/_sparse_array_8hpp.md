---
title: src/ecs/SparseArray.hpp

---

# src/ecs/SparseArray.hpp



## Namespaces

| Name           |
| -------------- |
| **[ecs](Namespaces/namespaceecs.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[ecs::SparseArray](Classes/classecs_1_1_sparse_array.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** SparseArray
*/

#pragma once

#include <exception>
#include <iostream>
#include <optional>
#include <vector>
#include "Constant.hpp"

namespace ecs
{
    template <typename Component> class SparseArray {
      public:
        using valueType = std::optional<Component>;
        using referenceType = valueType &;
        using constReferenceType = valueType const &;
        using container = std::vector<valueType>;
        using sizeType = typename container::size_type;
        using iterator = typename container::iterator;
        using constIterator = typename container::const_iterator;

      public:
        SparseArray() { _data.clear(); }
        SparseArray(SparseArray const &other) : _data(other._data) {}
        SparseArray(SparseArray &&other) noexcept : _data(std::move(other._data)) {}
        ~SparseArray() = default;

        SparseArray &operator=(SparseArray const &other)
        {
            for (auto &&i : other) {
                _data.insert(other);
            }
            return *this;
        }

        SparseArray &operator=(SparseArray &&other) noexcept
        {
            _data = std::move(other._data);
            return *this;
        }

        referenceType operator[](size_t idx) { return _data[idx]; }

        constReferenceType operator[](size_t idx) const { return _data[idx]; }

        iterator begin() { return _data.begin(); }

        constIterator begin() const { return _data.begin(); }

        constIterator cBegin() const { return _data.cbegin(); }

        iterator end() { return _data.end(); }

        constIterator end() const { return _data.end(); }

        constIterator cEnd() const { return _data.cend(); }

        sizeType size() const { return _data.size(); }

        referenceType insertAt(sizeType pos, Component const &c)
        {
            if (pos >= _data.size())
                _data.resize(pos + 1, std::nullopt);
            _data.at(pos) = c;
            return _data[pos];
        }

        referenceType insertAt(sizeType pos, Component &&c)
        {
            if (pos >= _data.size())
                _data.resize(pos + 1, std::nullopt);
            _data.at(pos) = c;
            return _data[pos];
        }

        template <class... Params> referenceType emplaceAt(sizeType pos, Params &&...args)
        {
            if (pos >= _data.size())
                _data.resize(pos + 1, std::nullopt);
            _data.at(pos) = Component(args...);
            return _data[pos];
        }

        void erase(sizeType pos)
        {
            if (pos < _data.size())
                if (_data[pos])
                    _data[pos] = std::nullopt;
        }

        sizeType getIndex(valueType const &c) const
        {
            std::size_t cpt = 0;
            if (!c.has_value())
                return utils::constant::npos;
            for (valueType iterator = _data.begin(); iterator != _data.end(); iterator++, cpt++)
                if (iterator.has_value() && iterator.value() == c.value()) {
                    return cpt;
                }
            return utils::constant::npos;
        }

      private:
        container _data;
    };
} // namespace ecs
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100
