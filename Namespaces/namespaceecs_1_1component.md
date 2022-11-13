---
title: ecs::component

---

# ecs::component



## Classes

|                | Name           |
| -------------- | -------------- |
| struct | **[ecs::component::Activable](Classes/structecs_1_1component_1_1_activable.md)**  |
| struct | **[ecs::component::Animated](Classes/structecs_1_1component_1_1_animated.md)**  |
| struct | **[ecs::component::AttackAI](Classes/structecs_1_1component_1_1_attack_a_i.md)** <br>[AttackAI]() component.  |
| struct | **[ecs::component::Controllable](Classes/structecs_1_1component_1_1_controllable.md)**  |
| struct | **[ecs::component::Direction](Classes/structecs_1_1component_1_1_direction.md)**  |
| struct | **[ecs::component::Drawable](Classes/structecs_1_1component_1_1_drawable.md)**  |
| struct | **[ecs::component::EntityType](Classes/structecs_1_1component_1_1_entity_type.md)** <br>[EntityType]() component.  |
| struct | **[ecs::component::Faction](Classes/structecs_1_1component_1_1_faction.md)**  |
| struct | **[ecs::component::FollowEntity](Classes/structecs_1_1component_1_1_follow_entity.md)**  |
| struct | **[ecs::component::Health](Classes/structecs_1_1component_1_1_health.md)**  |
| struct | **[ecs::component::Hitbox](Classes/structecs_1_1component_1_1_hitbox.md)**  |
| struct | **[ecs::component::MovementAI](Classes/structecs_1_1component_1_1_movement_a_i.md)** <br>[MovementAI]() component.  |
| struct | **[ecs::component::NetworkId](Classes/structecs_1_1component_1_1_network_id.md)** <br>[NetworkId]() component related to the entity sent to the client.  |
| struct | **[ecs::component::Parallax](Classes/structecs_1_1component_1_1_parallax.md)**  |
| struct | **[ecs::component::Position](Classes/structecs_1_1component_1_1_position.md)**  |
| struct | **[ecs::component::Projectile](Classes/structecs_1_1component_1_1_projectile.md)**  |
| struct | **[ecs::component::Score](Classes/structecs_1_1component_1_1_score.md)**  |
| struct | **[ecs::component::Shootable](Classes/structecs_1_1component_1_1_shootable.md)**  |
| struct | **[ecs::component::Size](Classes/structecs_1_1component_1_1_size.md)** <br>[Size]() component.  |
| struct | **[ecs::component::Text](Classes/structecs_1_1component_1_1_text.md)**  |
| struct | **[ecs::component::textColor](Classes/structecs_1_1component_1_1text_color.md)**  |
| struct | **[ecs::component::Velocity](Classes/structecs_1_1component_1_1_velocity.md)** <br>[Velocity]() component.  |
| struct | **[ecs::component::Weapon](Classes/structecs_1_1component_1_1_weapon.md)**  |

## Attributes

|                | Name           |
| -------------- | -------------- |
| const std::pair< char, char > | **[STOP](Namespaces/namespaceecs_1_1component.md#variable-stop)**  |
| const std::pair< char, char > | **[UP](Namespaces/namespaceecs_1_1component.md#variable-up)**  |
| const std::pair< char, char > | **[UP_LEFT](Namespaces/namespaceecs_1_1component.md#variable-up-left)**  |
| const std::pair< char, char > | **[LEFT](Namespaces/namespaceecs_1_1component.md#variable-left)**  |
| const std::pair< char, char > | **[DOWN_LEFT](Namespaces/namespaceecs_1_1component.md#variable-down-left)**  |
| const std::pair< char, char > | **[DOWN](Namespaces/namespaceecs_1_1component.md#variable-down)**  |
| const std::pair< char, char > | **[DOWN_RIGHT](Namespaces/namespaceecs_1_1component.md#variable-down-right)**  |
| const std::pair< char, char > | **[RIGHT](Namespaces/namespaceecs_1_1component.md#variable-right)**  |
| const std::pair< char, char > | **[UP_RIGHT](Namespaces/namespaceecs_1_1component.md#variable-up-right)**  |



## Attributes Documentation

### variable STOP

```cpp
static const std::pair< char, char > STOP = {0, 0};
```


### variable UP

```cpp
static const std::pair< char, char > UP = {0, -1};
```


### variable UP_LEFT

```cpp
static const std::pair< char, char > UP_LEFT = {-1, -1};
```


### variable LEFT

```cpp
static const std::pair< char, char > LEFT = {-1, 0};
```


### variable DOWN_LEFT

```cpp
static const std::pair< char, char > DOWN_LEFT = {-1, 1};
```


### variable DOWN

```cpp
static const std::pair< char, char > DOWN = {0, 1};
```


### variable DOWN_RIGHT

```cpp
static const std::pair< char, char > DOWN_RIGHT = {1, 1};
```


### variable RIGHT

```cpp
static const std::pair< char, char > RIGHT = {1, 0};
```


### variable UP_RIGHT

```cpp
static const std::pair< char, char > UP_RIGHT = {1, -1};
```





-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100