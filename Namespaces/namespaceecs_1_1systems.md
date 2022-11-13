---
title: ecs::systems

---

# ecs::systems



## Functions

|                | Name           |
| -------------- | -------------- |
| void | **[movePacketHandle](Namespaces/namespaceecs_1_1systems.md#function-movepackethandle)**([World](Classes/classecs_1_1_world.md) & world, [network::Message](Namespaces/namespacenetwork.md#typedef-message) & msg) |
| void | **[firstMessageHandle](Namespaces/namespaceecs_1_1systems.md#function-firstmessagehandle)**([World](Classes/classecs_1_1_world.md) & world, [network::Message](Namespaces/namespacenetwork.md#typedef-message) & msg) |
| void | **[deathMessageHandle](Namespaces/namespaceecs_1_1systems.md#function-deathmessagehandle)**([World](Classes/classecs_1_1_world.md) & world, [network::Message](Namespaces/namespacenetwork.md#typedef-message) & msg) |
| void | **[playerHealthHandle](Namespaces/namespaceecs_1_1systems.md#function-playerhealthhandle)**([World](Classes/classecs_1_1_world.md) & world, [network::Message](Namespaces/namespacenetwork.md#typedef-message) & msg) |
| void | **[createPlayer](Namespaces/namespaceecs_1_1systems.md#function-createplayer)**([World](Classes/classecs_1_1_world.md) & world, [network::ClientMessage](Namespaces/namespacenetwork.md#typedef-clientmessage) & msg) |
| void | **[movePlayer](Namespaces/namespaceecs_1_1systems.md#function-moveplayer)**([World](Classes/classecs_1_1_world.md) & world, [network::ClientMessage](Namespaces/namespacenetwork.md#typedef-clientmessage) & msg) |
| void | **[playerShoot](Namespaces/namespaceecs_1_1systems.md#function-playershoot)**([World](Classes/classecs_1_1_world.md) & world, [network::ClientMessage](Namespaces/namespacenetwork.md#typedef-clientmessage) & msg) |

## Attributes

|                | Name           |
| -------------- | -------------- |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[animate](Namespaces/namespaceecs_1_1systems.md#variable-animate)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[draw](Namespaces/namespaceecs_1_1systems.md#variable-draw)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[executeOnce](Namespaces/namespaceecs_1_1systems.md#variable-executeonce)**  |
| size_t | **[selfId](Namespaces/namespaceecs_1_1systems.md#variable-selfid)**  |
| std::unordered_map< char, std::function< void([World](Classes/classecs_1_1_world.md) &, [network::Message](Namespaces/namespacenetwork.md#typedef-message) &msg)> > | **[packetTypeFunction](Namespaces/namespaceecs_1_1systems.md#variable-packettypefunction)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[HandleIncomingMessages](Namespaces/namespaceecs_1_1systems.md#variable-handleincomingmessages)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[HandleParallaxBounds](Namespaces/namespaceecs_1_1systems.md#variable-handleparallaxbounds)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[handleSFMLEvents](Namespaces/namespaceecs_1_1systems.md#variable-handlesfmlevents)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[handleSFMLKeys](Namespaces/namespaceecs_1_1systems.md#variable-handlesfmlkeys)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[healthBar](Namespaces/namespaceecs_1_1systems.md#variable-healthbar)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[menuSelect](Namespaces/namespaceecs_1_1systems.md#variable-menuselect)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[scoreUpdate](Namespaces/namespaceecs_1_1systems.md#variable-scoreupdate)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[SendDirection](Namespaces/namespaceecs_1_1systems.md#variable-senddirection)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[manageClientEvents](Namespaces/namespaceecs_1_1systems.md#variable-manageclientevents)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[movement](Namespaces/namespaceecs_1_1systems.md#variable-movement)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[positionLogger](Namespaces/namespaceecs_1_1systems.md#variable-positionlogger)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[runMovementAI](Namespaces/namespaceecs_1_1systems.md#variable-runmovementai)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[deathUpdate](Namespaces/namespaceecs_1_1systems.md#variable-deathupdate)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[followEntitySystem](Namespaces/namespaceecs_1_1systems.md#variable-followentitysystem)**  |
| std::map< unsigned int, size_t > | **[clientNumToId](Namespaces/namespaceecs_1_1systems.md#variable-clientnumtoid)**  |
| std::unordered_map< char, std::function< void([World](Classes/classecs_1_1_world.md) &, [network::ClientMessage](Namespaces/namespacenetwork.md#typedef-clientmessage) &msg)> > | **[packetTypeFunction](Namespaces/namespaceecs_1_1systems.md#variable-packettypefunction)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[playerHealthUpdate](Namespaces/namespaceecs_1_1systems.md#variable-playerhealthupdate)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[PositionUpdate](Namespaces/namespaceecs_1_1systems.md#variable-positionupdate)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[projectileCollision](Namespaces/namespaceecs_1_1systems.md#variable-projectilecollision)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[runAttackAI](Namespaces/namespaceecs_1_1systems.md#variable-runattackai)**  |
| std::function< void([World](Classes/classecs_1_1_world.md) &)> | **[waves](Namespaces/namespaceecs_1_1systems.md#variable-waves)**  |


## Functions Documentation

### function movePacketHandle

```cpp
static void movePacketHandle(
    World & world,
    network::Message & msg
)
```


### function firstMessageHandle

```cpp
static void firstMessageHandle(
    World & world,
    network::Message & msg
)
```


### function deathMessageHandle

```cpp
static void deathMessageHandle(
    World & world,
    network::Message & msg
)
```


### function playerHealthHandle

```cpp
static void playerHealthHandle(
    World & world,
    network::Message & msg
)
```


### function createPlayer

```cpp
static void createPlayer(
    World & world,
    network::ClientMessage & msg
)
```


**Parameters**: 

  * **world** The world in which we want to operate 
  * **msg** The message of a new player coming on the server 


In goal of create a player, first, we need to add every components of the player. Specify to the server that there is a new connection and check if the request has been accepted 


### function movePlayer

```cpp
static void movePlayer(
    World & world,
    network::ClientMessage & msg
)
```


**Parameters**: 

  * **world** The world we want to operate 
  * **msg** The message containing the new position of the player 


Updating the player position according to the given msg 


### function playerShoot

```cpp
static void playerShoot(
    World & world,
    network::ClientMessage & msg
)
```


**Parameters**: 

  * **world** The world we want to operate 
  * **msg** Only used to compare ID and select the correct player 


Used to make the player shoot from the given message 



## Attributes Documentation

### variable animate

```cpp
std::function< void(World &)> animate = [](World &world) {
        auto &animateds = world.registry.getComponents<component::Animated>();

        using chrono = std::chrono::high_resolution_clock;
        using chronoDuration = std::chrono::duration<double, std::milli>;
        for (size_t i = 0; i < animateds.size(); ++i) {
            auto &anim = animateds[i];

            if (anim) {
                if (chrono::now().time_since_epoch().count() - anim.value().lastSwitch
                    > static_cast<size_t>(anim.value().getFrame().delay) * 1000000) {
                    anim.value().nextFrame();
                    anim.value().lastSwitch = chrono::now().time_since_epoch().count();
                }
            }
        }
    };
```


### variable draw

```cpp
std::function< void(World &)> draw;
```


Used to set the scale, the position and the texture of the entity before display it 


### variable executeOnce

```cpp
std::function< void(World &)> executeOnce = [](World &world) {
        static bool executed = false;

        if (!executed) {
            network::Message msg;
            msg.fill(0);
            network::Client::connect();
            network::Client::getOutgoingMessages().push(msg);
            executed = true;
        }
    };
```


Login to the server only once 


### variable selfId

```cpp
static size_t selfId = 0;
```


### variable packetTypeFunction

```cpp
static std::unordered_map< char, std::function< void(World &, network::Message &msg)> > packetTypeFunction = {
        {utils::constant::getPacketTypeKey(utils::constant::PacketType::ENTITY_MOVE), movePacketHandle},
        {0, firstMessageHandle},
        {utils::constant::getPacketTypeKey(utils::constant::PacketType::ENTITY_DEATH), deathMessageHandle},
        {utils::constant::getPacketTypeKey(utils::constant::PacketType::HEALTH_UPDATE), playerHealthHandle}};
```


### variable HandleIncomingMessages

```cpp
std::function< void(World &)> HandleIncomingMessages = [](World &world) {
        while (!network::Client::getReceivedMessages().empty()) {
            network::Message msg = network::Client::getReceivedMessages().pop();
            if (packetTypeFunction.find(msg[0]) != packetTypeFunction.end())
                packetTypeFunction[msg[0]](world, msg);
        }
    };
```


### variable HandleParallaxBounds

```cpp
std::function< void(World &)> HandleParallaxBounds = [](World &world) {
        auto &parallaxes = world.registry.getComponents<component::Parallax>();
        auto &positions = world.registry.getComponents<component::Position>();

        for (size_t i = 0; i < parallaxes.size() && i < positions.size(); i++) {
            if (!parallaxes[i] || !positions[i])
                continue;
            if (positions[i].value().x < parallaxes[i].value().threshold) {
                positions[i].value().x += parallaxes[i].value().position;
            }
        }
    };
```


### variable handleSFMLEvents

```cpp
std::function< void(World &)> handleSFMLEvents;
```


Used to manage Sfml events Currently able to manage the following actions: Close the window KeyPressed, in this case, we check if the bind is known from sfml: if yes, we had it on world's events' stack, nothing otherwise 


### variable handleSFMLKeys

```cpp
std::function< void(World &)> handleSFMLKeys;
```


Used to manage every action ordered by Sfml input by the user Refer to the [Controllable.hpp](Files/_controllable_8hpp.md#file-controllable.hpp) documentation to learn more about managed input 


### variable healthBar

```cpp
std::function< void(World &)> healthBar = [](World &world) {

        auto const &positions = world.registry.getComponents<component::Position>();
        auto &sizes = world.registry.getComponents<component::Size>();
        auto const &healths = world.registry.getComponents<component::Health>();

        for (size_t i = 0; i < positions.size() && i < sizes.size() && i < healths.size(); i++) {
            auto const &pos = positions[i];
            auto &size = sizes[i];
            auto const &health = healths[i];

            if (pos && size && health) {
                if (health->health >= 0 && health->health < utils::constant::maxPlayerHealth) {
                    size.value().width = utils::constant::sizeHealthBar * health->health / 100;
                } else if (health->health < 0)
                    size.value().width = 0;
                else
                    size.value().width = utils::constant::sizeHealthBar;
            }

        }
    };
```


### variable menuSelect

```cpp
std::function< void(World &)> menuSelect;
```


### variable scoreUpdate

```cpp
std::function< void(World &)> scoreUpdate = [](World &world) {
      auto &texts = world.registry.getComponents<component::Text>();
      auto &scores = world.registry.getComponents<component::Score>();

      for (size_t i = 0; i < texts.size() || i < scores.size(); i++) {
          auto &text = texts[i];
          auto &score = scores[i];

          if (text && score) {
              std::chrono::steady_clock::time_point end = std::chrono::steady_clock::now();
              auto time = std::chrono::duration_cast<std::chrono::milliseconds>(end - begin).count() / 10;
              auto elapsed = std::to_string(time);
              const std::string string = "Score: ";

              text->setContent(0, string);
              text->setContent(1, elapsed);
              score->setScore(time);
          }
      }
    };
```


Used to set the score of the player 


### variable SendDirection

```cpp
std::function< void(World &)> SendDirection = [](World &world) {
        auto const &controllables = world.registry.getComponents<component::Controllable>();
        auto &directions = world.registry.getComponents<component::Direction>();

        static auto clock = utils::constant::chrono::now();
        if (utils::constant::chronoDuration(utils::constant::chrono::now() - clock).count() > 10) {
            clock = utils::constant::chrono::now();
            for (size_t i = 0; i < controllables.size() && i < directions.size(); i++) {
                if (!controllables[i] || !directions[i])
                    continue;

                if (directions[i].value().hasMoved) {
                    network::Message msg;
                    msg.fill(0);
                    msg[0] = utils::constant::PLAYER_MOVE;
                    msg[1] = directions[i].value().x;
                    msg[2] = directions[i].value().y;
                    network::Client::getOutgoingMessages().push(msg);
                    directions[i].value().hasMoved = false;
                }
            }
        }
    };
```


Send direction system used to fill the array of messages to the server regarding the direction of the player 


### variable manageClientEvents

```cpp
std::function< void(World &)> manageClientEvents;
```


Used to manage every client' events Refer to SFMLEvents.hpp documentation to learn more about managed events 


### variable movement

```cpp
std::function< void(World &)> movement;
```


Used to apply the values of the velocity component to the position component according to the internal clock of the system 


### variable positionLogger

```cpp
std::function< void(World &)> positionLogger = [](World &world) {
        auto const &positions = world.registry.getComponents<component::Position>();
        auto const &velocities = world.registry.getComponents<component::Velocity>();

        for (size_t i = 0; i < positions.size() && i < velocities.size(); ++i) {
            auto const &pos = positions[i];
            auto const &vel = velocities[i];
            if (pos && vel) {
                std ::cerr << i << ": Position = { " << pos.value().x << ", " << pos.value().y << " }, Velocity = { "
                           << vel.value().x << ", " << vel.value().y << " } " << std ::endl;
            }
        };
    };
```


Used to display, as a logger, all the value of the Position & Velocity component 


### variable runMovementAI

```cpp
std::function< void(World &)> runMovementAI = [](World &world) {
        auto &directions = world.registry.getComponents<component::Direction>();
        auto &movementAIs = world.registry.getComponents<component::MovementAI>();

        using chrono = std::chrono::high_resolution_clock;
        using chronoDuration = std::chrono::duration<double, std::milli>;

        for (size_t i = 0; i < directions.size() && i < movementAIs.size(); ++i) {
            auto &dir = directions[i];
            auto &movAI = movementAIs[i];

            if (dir && movAI) {
                if ((chrono::now().time_since_epoch().count() - movAI.value().getLastMovement()) / 10000000
                    > static_cast<size_t>(movAI.value().getDelay())) {
                    auto &tmpDir = movAI.value().getNextDirection();
                    dir.value().x = tmpDir.first;
                    dir.value().y = tmpDir.second;
                    dir.value().hasMoved = true;
                    movAI.value().setLastMovement(chrono::now().time_since_epoch().count());
                }
            }
        };
    };
```


Runs the AIs stored in the enities 


### variable deathUpdate

```cpp
std::function< void(World &)> deathUpdate;
```


System used to push death of entity message to the server outgoing queue when is life as gone under 0. 


### variable followEntitySystem

```cpp
std::function< void(World &)> followEntitySystem = [](World &world) {
        auto &positions = world.registry.getComponents<component::Position>();
        auto const &follows = world.registry.getComponents<component::FollowEntity>();

        for (std::size_t i = 0; i < positions.size() && i < follows.size(); i++) {
            auto &pos = positions[i];
            auto const &fol = follows[i];

            if (pos && fol) {
                if (fol.value().entityId < positions.size()) {
                    if (positions[fol.value().entityId]) {
                        pos.value().x = positions[fol.value().entityId].value().x - 50;
                        pos.value().y = positions[fol.value().entityId].value().y + 50;
                    }
                }
            }
        }
    };
```


### variable clientNumToId

```cpp
static std::map< unsigned int, size_t > clientNumToId = {};
```


### variable packetTypeFunction

```cpp
static std::unordered_map< char, std::function< void(World &, network::ClientMessage &msg)> > packetTypeFunction = {
        {0, createPlayer}, {utils::constant::PLAYER_MOVE, movePlayer}, {utils::constant::PLAYER_SHOT, playerShoot}};
```


### variable playerHealthUpdate

```cpp
std::function< void(World &)> playerHealthUpdate = [](World &world) {
        auto &healths = world.registry.getComponents<component::Health>();
        auto &networkId = world.registry.getComponents<component::NetworkId>();
        auto &entity = world.registry.getComponents<component::EntityType>();
        for (size_t i = 0; i < healths.size(); ++i) {
            auto &health = healths[i];
            if (health && health.value().health != health.value().lastHealth) {
                if (i < entity.size() && i < networkId.size()) {
                    auto &type = entity[i];
                    auto &id = networkId[i];
                    if (type && id && type.value().type == component::EntityType::Types::Player) {
                        health.value().lastHealth = health.value().health;
                        std::array<char, 2> idBin = id.value().serialize();
                        network::Message msg;
                        msg[0] = utils::constant::getPacketTypeKey(utils::constant::PacketType::HEALTH_UPDATE);
                        msg[1] = idBin[0];
                        msg[2] = idBin[1];
                        msg[3] = health.value().health;
                        network::Server::getOutgoingMessages().push(
                            network::ServerMessage(msg, std::vector<unsigned int>()));
                    }
                }
            }
        }
    };
```


System used to push death of entity message to the server outgoing queue when is life as gone under 0. 


### variable PositionUpdate

```cpp
std::function< void(World &)> PositionUpdate;
```


System used to push updated position of entity to the server outgoing queue. 


### variable projectileCollision

```cpp
std::function< void(World &)> projectileCollision;
```


### variable runAttackAI

```cpp
std::function< void(World &)> runAttackAI;
```


Runs the AIs stored in the enities 


### variable waves

```cpp
std::function< void(World &)> waves;
```





-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100