---
title: src/ecs/LockedQueue.hpp

---

# src/ecs/LockedQueue.hpp



## Namespaces

| Name           |
| -------------- |
| **[network](Namespaces/namespacenetwork.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[network::LockedQueue](Classes/classnetwork_1_1_locked_queue.md)**  |




## Source code

```cpp
/*
** EPITECH PROJECT, 2022
** RTYPE
** File description:
** LockedQueue
*/

#pragma once
#include <list>
#include <mutex>
#include <queue>

namespace network
{
    typedef std::array<char, 16> Message;
    typedef std::pair<Message, unsigned int> ClientMessage;
    typedef std::pair<Message, std::vector<unsigned int>> ServerMessage;

    template <typename T> class LockedQueue {
      private:
        std::mutex mutex;
        std::queue<T> queue;

      public:
        void push(T value)
        {
            std::unique_lock<std::mutex> lock(mutex);
            queue.push(value);
        };

        T pop()
        {
            std::unique_lock<std::mutex> lock(mutex);
            T value;
            std::swap(value, queue.front());
            queue.pop();
            return value;
        };

        bool empty()
        {
            std::unique_lock<std::mutex> lock(mutex);
            return queue.empty();
        }
    };
}
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100
