---
title: ecs::EnemyFactory

---

# ecs::EnemyFactory






`#include <EnemyFactory.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| enum| **[EnemyType](Classes/classecs_1_1_enemy_factory.md#enum-enemytype)** { Battlecruiser, Dreadnought, Fighter, Frigate, Scout, Torpedo, NoodleMonster} |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| void | **[spawnEnemy](Classes/classecs_1_1_enemy_factory.md#function-spawnenemy)**([ecs::World](Classes/classecs_1_1_world.md) & world, [EnemyType](Classes/classecs_1_1_enemy_factory.md#enum-enemytype) type, int posX, int posY, [component::Faction::Factions](Classes/structecs_1_1component_1_1_faction.md#enum-factions) fac, [component::MovementAI::AIType](Classes/structecs_1_1component_1_1_movement_a_i.md#enum-aitype) movAI) |

## Public Types Documentation

### enum EnemyType

| Enumerator | Value | Description |
| ---------- | ----- | ----------- |
| Battlecruiser | |   |
| Dreadnought | |   |
| Fighter | |   |
| Frigate | |   |
| Scout | |   |
| Torpedo | |   |
| NoodleMonster | |   |




## Public Functions Documentation

### function spawnEnemy

```cpp
static inline void spawnEnemy(
    ecs::World & world,
    EnemyType type,
    int posX,
    int posY,
    component::Faction::Factions fac,
    component::MovementAI::AIType movAI
)
```


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100