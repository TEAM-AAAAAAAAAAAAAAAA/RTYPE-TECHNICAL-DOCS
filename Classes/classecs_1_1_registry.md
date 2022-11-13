---
title: ecs::Registry

---

# ecs::Registry



 [More...](#detailed-description)


`#include <Registry.hpp>`

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[Registry](Classes/classecs_1_1_registry.md#function-registry)**() |
| template <class Component \> <br>[SparseArray](Classes/classecs_1_1_sparse_array.md)< Component > & | **[registerComponent](Classes/classecs_1_1_registry.md#function-registercomponent)**() |
| template <class Component \> <br>[SparseArray](Classes/classecs_1_1_sparse_array.md)< Component > & | **[getComponents](Classes/classecs_1_1_registry.md#function-getcomponents)**() |
| template <class Component \> <br>[SparseArray](Classes/classecs_1_1_sparse_array.md)< Component > const & | **[getComponents](Classes/classecs_1_1_registry.md#function-getcomponents)**() const |
| [Entity](Classes/classecs_1_1_entity.md) | **[spawn_entity](Classes/classecs_1_1_registry.md#function-spawn-entity)**() |
| [Entity](Classes/classecs_1_1_entity.md) | **[entityFromIndex](Classes/classecs_1_1_registry.md#function-entityfromindex)**(std::size_t idx) |
| void | **[killEntity](Classes/classecs_1_1_registry.md#function-killentity)**([Entity](Classes/classecs_1_1_entity.md) const & e) |
| template <typename Component \> <br>[SparseArray](Classes/classecs_1_1_sparse_array.md)< Component >::referenceType | **[addComponent](Classes/classecs_1_1_registry.md#function-addcomponent)**([Entity](Classes/classecs_1_1_entity.md) const & to, Component && c) |
| template <typename Component ,typename... Params\> <br>[SparseArray](Classes/classecs_1_1_sparse_array.md)< Component >::referenceType | **[emplaceComponent](Classes/classecs_1_1_registry.md#function-emplacecomponent)**([Entity](Classes/classecs_1_1_entity.md) const & to, Params &&... p) |
| template <typename Component \> <br>void | **[removeComponent](Classes/classecs_1_1_registry.md#function-removecomponent)**([Entity](Classes/classecs_1_1_entity.md) const & from) |

## Detailed Description

```cpp
class ecs::Registry;
```


[This is the core of the ECS] 

This class contains many feature as follows : 


* Component Manager, [Registry](Classes/classecs_1_1_registry.md) is able to register/get components from the unordered map
* [Entity](Classes/classecs_1_1_entity.md) Manager, [Registry](Classes/classecs_1_1_registry.md) is able to create/delete and add component to an [Entity](Classes/classecs_1_1_entity.md)

 (Feel free to check the [Entity.hpp](Files/_entity_8hpp.md#file-entity.hpp) to learn more about the subject)
* EntitiesBin Manager, [Registry](Classes/classecs_1_1_registry.md) is saving killed entity in the bin that which can be recovered instead of creating another one

## Public Functions Documentation

### function Registry

```cpp
inline Registry()
```


### function registerComponent

```cpp
template <class Component >
inline SparseArray< Component > & registerComponent()
```


**Template Parameters**: 

  * **Component** The type of components you want to register 


**Return**: The [SparseArray](Classes/classecs_1_1_sparse_array.md) of components you just registered 

This function is used to register a new component in the private member _unordered_map 


### function getComponents

```cpp
template <class Component >
inline SparseArray< Component > & getComponents()
```


**Template Parameters**: 

  * **Component** The type of components you want to get 


**Return**: The [SparseArray](Classes/classecs_1_1_sparse_array.md) of components you asked 

This function is used to get all components already registered in the [Registry](Classes/classecs_1_1_registry.md) class following the given component template 


### function getComponents

```cpp
template <class Component >
inline SparseArray< Component > const & getComponents() const
```


**Template Parameters**: 

  * **Component** The type of components you want to get 


**Return**: The const [SparseArray](Classes/classecs_1_1_sparse_array.md) of components you asked 

This function is used to get all components already registered in the [Registry](Classes/classecs_1_1_registry.md) class following the given component template as const 


### function spawn_entity

```cpp
inline Entity spawn_entity()
```


**Return**: The entity just created (id) 

This function is used to create a new entity if it doesn't exists in the _entitiesBin, otherwise it recover it from the bin 


### function entityFromIndex

```cpp
inline Entity entityFromIndex(
    std::size_t idx
)
```


**Parameters**: 

  * **idx** The index of the entity whose id is desired 


**Return**: The id of the [Entity](Classes/classecs_1_1_entity.md) if it exists, ecs::npos otherwise 

This function is used to get the id of the [Entity](Classes/classecs_1_1_entity.md) following the give index 


### function killEntity

```cpp
inline void killEntity(
    Entity const & e
)
```


**Parameters**: 

  * **e** The [Entity](Classes/classecs_1_1_entity.md) you want to kill 


This is used to delete the given [Entity](Classes/classecs_1_1_entity.md) (id) For optimisation purposes, [Registry](Classes/classecs_1_1_registry.md) class push it in the _entitiesBin 


### function addComponent

```cpp
template <typename Component >
inline SparseArray< Component >::referenceType addComponent(
    Entity const & to,
    Component && c
)
```


**Parameters**: 

  * **to** The [Entity](Classes/classecs_1_1_entity.md) in which you want to add component 
  * **c** The component you want to add 


**Template Parameters**: 

  * **Component** The type of component want to be added 


**Return**: the SparseArray<Component> reference of the component 

This function is used to add a component into the [Entity](Classes/classecs_1_1_entity.md) given as parameter. In the same time, the erase function of this component is pushed into the _eraseFunctions vector, in this case we can simply delete a component without needing type of it 


### function emplaceComponent

```cpp
template <typename Component ,
typename... Params>
inline SparseArray< Component >::referenceType emplaceComponent(
    Entity const & to,
    Params &&... p
)
```


**Parameters**: 

  * **to** The [Entity](Classes/classecs_1_1_entity.md) in which you want to emplace component 
  * **p** Parameters of the component you want to emplace 


**Template Parameters**: 

  * **Component** The type of component you want to emplace 
  * **Params** The parameters' type of the component you want to emplace 


**Return**: the SparseArray<Component> reference of the component 

This function is used to emplace a component with given parameters of this component 


### function removeComponent

```cpp
template <typename Component >
inline void removeComponent(
    Entity const & from
)
```


**Parameters**: 

  * **from** The [Entity](Classes/classecs_1_1_entity.md) in which you want to remove component 


**Template Parameters**: 

  * **Component** The type of the component you want to remove 


This function is used to remove a component into an [Entity](Classes/classecs_1_1_entity.md) given as parameter 


-------------------------------

Updated on 2022-11-13 at 17:15:13 +0100