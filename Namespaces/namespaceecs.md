---
title: ecs

---

# ecs

 [More...](#detailed-description)

## Namespaces

| Name           |
| -------------- |
| **[ecs::component](Namespaces/namespaceecs_1_1component.md)**  |
| **[ecs::systems](Namespaces/namespaceecs_1_1systems.md)**  |

## Classes

|                | Name           |
| -------------- | -------------- |
| class | **[ecs::EnemyFactory](Classes/classecs_1_1_enemy_factory.md)**  |
| class | **[ecs::Engine](Classes/classecs_1_1_engine.md)**  |
| class | **[ecs::Entity](Classes/classecs_1_1_entity.md)**  |
| class | **[ecs::Event](Classes/classecs_1_1_event.md)**  |
| class | **[ecs::Registry](Classes/classecs_1_1_registry.md)**  |
| class | **[ecs::SparseArray](Classes/classecs_1_1_sparse_array.md)**  |
| class | **[ecs::World](Classes/classecs_1_1_world.md)**  |
| class | **[ecs::WorldManager](Classes/classecs_1_1_world_manager.md)**  |

## Functions

|                | Name           |
| -------------- | -------------- |
| void | **[generateBattlecruiser](Namespaces/namespaceecs.md#function-generatebattlecruiser)**([ecs::World](Classes/classecs_1_1_world.md) & world, int posX, int posY, [component::Faction::Factions](Classes/structecs_1_1component_1_1_faction.md#enum-factions) fac, [component::MovementAI::AIType](Classes/structecs_1_1component_1_1_movement_a_i.md#enum-aitype) movAI) |
| void | **[generateDreadnought](Namespaces/namespaceecs.md#function-generatedreadnought)**([ecs::World](Classes/classecs_1_1_world.md) & world, int posX, int posY, [component::Faction::Factions](Classes/structecs_1_1component_1_1_faction.md#enum-factions) fac, [component::MovementAI::AIType](Classes/structecs_1_1component_1_1_movement_a_i.md#enum-aitype) movAI) |
| void | **[generateFighter](Namespaces/namespaceecs.md#function-generatefighter)**([ecs::World](Classes/classecs_1_1_world.md) & world, int posX, int posY, [component::Faction::Factions](Classes/structecs_1_1component_1_1_faction.md#enum-factions) fac, [component::MovementAI::AIType](Classes/structecs_1_1component_1_1_movement_a_i.md#enum-aitype) movAI) |
| void | **[generateFrigate](Namespaces/namespaceecs.md#function-generatefrigate)**([ecs::World](Classes/classecs_1_1_world.md) & world, int posX, int posY, [component::Faction::Factions](Classes/structecs_1_1component_1_1_faction.md#enum-factions) fac, [component::MovementAI::AIType](Classes/structecs_1_1component_1_1_movement_a_i.md#enum-aitype) movAI) |
| void | **[generateScout](Namespaces/namespaceecs.md#function-generatescout)**([ecs::World](Classes/classecs_1_1_world.md) & world, int posX, int posY, [component::Faction::Factions](Classes/structecs_1_1component_1_1_faction.md#enum-factions) fac, [component::MovementAI::AIType](Classes/structecs_1_1component_1_1_movement_a_i.md#enum-aitype) movAI) |
| void | **[generateTorpedo](Namespaces/namespaceecs.md#function-generatetorpedo)**([ecs::World](Classes/classecs_1_1_world.md) & world, int posX, int posY, [component::Faction::Factions](Classes/structecs_1_1component_1_1_faction.md#enum-factions) fac, [component::MovementAI::AIType](Classes/structecs_1_1component_1_1_movement_a_i.md#enum-aitype) movAI) |
| void | **[generateNoodleMonster](Namespaces/namespaceecs.md#function-generatenoodlemonster)**([ecs::World](Classes/classecs_1_1_world.md) & world, int posX, int posY, [component::Faction::Factions](Classes/structecs_1_1component_1_1_faction.md#enum-factions) fac, [component::MovementAI::AIType](Classes/structecs_1_1component_1_1_movement_a_i.md#enum-aitype) movAI) |

## Detailed Description


[Entity](Classes/classecs_1_1_entity.md) class is represented by a simple entity_t according to the global functioning of the ECS 


## Functions Documentation

### function generateBattlecruiser

```cpp
static void generateBattlecruiser(
    ecs::World & world,
    int posX,
    int posY,
    component::Faction::Factions fac,
    component::MovementAI::AIType movAI
)
```


### function generateDreadnought

```cpp
static void generateDreadnought(
    ecs::World & world,
    int posX,
    int posY,
    component::Faction::Factions fac,
    component::MovementAI::AIType movAI
)
```


### function generateFighter

```cpp
static void generateFighter(
    ecs::World & world,
    int posX,
    int posY,
    component::Faction::Factions fac,
    component::MovementAI::AIType movAI
)
```


### function generateFrigate

```cpp
static void generateFrigate(
    ecs::World & world,
    int posX,
    int posY,
    component::Faction::Factions fac,
    component::MovementAI::AIType movAI
)
```


### function generateScout

```cpp
static void generateScout(
    ecs::World & world,
    int posX,
    int posY,
    component::Faction::Factions fac,
    component::MovementAI::AIType movAI
)
```


### function generateTorpedo

```cpp
static void generateTorpedo(
    ecs::World & world,
    int posX,
    int posY,
    component::Faction::Factions fac,
    component::MovementAI::AIType movAI
)
```


### function generateNoodleMonster

```cpp
static void generateNoodleMonster(
    ecs::World & world,
    int posX,
    int posY,
    component::Faction::Factions fac,
    component::MovementAI::AIType movAI
)
```






-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100