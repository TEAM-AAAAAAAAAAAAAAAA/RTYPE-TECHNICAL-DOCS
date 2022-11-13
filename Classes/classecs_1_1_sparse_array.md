---
title: ecs::SparseArray

---

# ecs::SparseArray



 [More...](#detailed-description)


`#include <SparseArray.hpp>`

## Public Types

|                | Name           |
| -------------- | -------------- |
| using std::optional< Component > | **[valueType](Classes/classecs_1_1_sparse_array.md#using-valuetype)**  |
| using [valueType](Classes/classecs_1_1_sparse_array.md#using-valuetype) & | **[referenceType](Classes/classecs_1_1_sparse_array.md#using-referencetype)**  |
| using [valueType](Classes/classecs_1_1_sparse_array.md#using-valuetype) const & | **[constReferenceType](Classes/classecs_1_1_sparse_array.md#using-constreferencetype)**  |
| using std::vector< [valueType](Classes/classecs_1_1_sparse_array.md#using-valuetype) > | **[container](Classes/classecs_1_1_sparse_array.md#using-container)**  |
| using typename container::size_type | **[sizeType](Classes/classecs_1_1_sparse_array.md#using-sizetype)**  |
| using typename container::iterator | **[iterator](Classes/classecs_1_1_sparse_array.md#using-iterator)**  |
| using typename container::const_iterator | **[constIterator](Classes/classecs_1_1_sparse_array.md#using-constiterator)**  |

## Public Functions

|                | Name           |
| -------------- | -------------- |
| | **[SparseArray](Classes/classecs_1_1_sparse_array.md#function-sparsearray)**() |
| | **[SparseArray](Classes/classecs_1_1_sparse_array.md#function-sparsearray)**([SparseArray](Classes/classecs_1_1_sparse_array.md) const & other) |
| | **[SparseArray](Classes/classecs_1_1_sparse_array.md#function-sparsearray)**([SparseArray](Classes/classecs_1_1_sparse_array.md) && other) |
| | **[~SparseArray](Classes/classecs_1_1_sparse_array.md#function-~sparsearray)**() =default |
| [SparseArray](Classes/classecs_1_1_sparse_array.md) & | **[operator=](Classes/classecs_1_1_sparse_array.md#function-operator=)**([SparseArray](Classes/classecs_1_1_sparse_array.md) const & other) |
| [SparseArray](Classes/classecs_1_1_sparse_array.md) & | **[operator=](Classes/classecs_1_1_sparse_array.md#function-operator=)**([SparseArray](Classes/classecs_1_1_sparse_array.md) && other) |
| [referenceType](Classes/classecs_1_1_sparse_array.md#using-referencetype) | **[operator[]](Classes/classecs_1_1_sparse_array.md#function-operator[])**(size_t idx) |
| [constReferenceType](Classes/classecs_1_1_sparse_array.md#using-constreferencetype) | **[operator[]](Classes/classecs_1_1_sparse_array.md#function-operator[])**(size_t idx) const |
| [iterator](Classes/classecs_1_1_sparse_array.md#using-iterator) | **[begin](Classes/classecs_1_1_sparse_array.md#function-begin)**() |
| [constIterator](Classes/classecs_1_1_sparse_array.md#using-constiterator) | **[begin](Classes/classecs_1_1_sparse_array.md#function-begin)**() const |
| [constIterator](Classes/classecs_1_1_sparse_array.md#using-constiterator) | **[cBegin](Classes/classecs_1_1_sparse_array.md#function-cbegin)**() const |
| [iterator](Classes/classecs_1_1_sparse_array.md#using-iterator) | **[end](Classes/classecs_1_1_sparse_array.md#function-end)**() |
| [constIterator](Classes/classecs_1_1_sparse_array.md#using-constiterator) | **[end](Classes/classecs_1_1_sparse_array.md#function-end)**() const |
| [constIterator](Classes/classecs_1_1_sparse_array.md#using-constiterator) | **[cEnd](Classes/classecs_1_1_sparse_array.md#function-cend)**() const |
| [sizeType](Classes/classecs_1_1_sparse_array.md#using-sizetype) | **[size](Classes/classecs_1_1_sparse_array.md#function-size)**() const |
| [referenceType](Classes/classecs_1_1_sparse_array.md#using-referencetype) | **[insertAt](Classes/classecs_1_1_sparse_array.md#function-insertat)**([sizeType](Classes/classecs_1_1_sparse_array.md#using-sizetype) pos, Component const & c) |
| [referenceType](Classes/classecs_1_1_sparse_array.md#using-referencetype) | **[insertAt](Classes/classecs_1_1_sparse_array.md#function-insertat)**([sizeType](Classes/classecs_1_1_sparse_array.md#using-sizetype) pos, Component && c) |
| template <class... Params\> <br>[referenceType](Classes/classecs_1_1_sparse_array.md#using-referencetype) | **[emplaceAt](Classes/classecs_1_1_sparse_array.md#function-emplaceat)**([sizeType](Classes/classecs_1_1_sparse_array.md#using-sizetype) pos, Params &&... args) |
| void | **[erase](Classes/classecs_1_1_sparse_array.md#function-erase)**([sizeType](Classes/classecs_1_1_sparse_array.md#using-sizetype) pos) |
| [sizeType](Classes/classecs_1_1_sparse_array.md#using-sizetype) | **[getIndex](Classes/classecs_1_1_sparse_array.md#function-getindex)**([valueType](Classes/classecs_1_1_sparse_array.md#using-valuetype) const & c) const |

## Detailed Description

```cpp
template <typename Component >
class ecs::SparseArray;
```


**Template Parameters**: 

  * **Component** The type of component used as with template 


[SparseArray](Classes/classecs_1_1_sparse_array.md) class is the component container of the ecs. 

This can be quite useful to store components that are defined for most entities, because you don't have to store the entity ID alongside the component. 

## Public Types Documentation

### using valueType

```cpp
using ecs::SparseArray< Component >::valueType =  std::optional<Component>;
```


### using referenceType

```cpp
using ecs::SparseArray< Component >::referenceType =  valueType &;
```


### using constReferenceType

```cpp
using ecs::SparseArray< Component >::constReferenceType =  valueType const &;
```


### using container

```cpp
using ecs::SparseArray< Component >::container =  std::vector<valueType>;
```


### using sizeType

```cpp
using ecs::SparseArray< Component >::sizeType =  typename container::size_type;
```


### using iterator

```cpp
using ecs::SparseArray< Component >::iterator =  typename container::iterator;
```


### using constIterator

```cpp
using ecs::SparseArray< Component >::constIterator =  typename container::const_iterator;
```


## Public Functions Documentation

### function SparseArray

```cpp
inline SparseArray()
```


Default constructor & destructor of the [SparseArray](Classes/classecs_1_1_sparse_array.md) class 


### function SparseArray

```cpp
inline SparseArray(
    SparseArray const & other
)
```


### function SparseArray

```cpp
inline SparseArray(
    SparseArray && other
)
```


### function ~SparseArray

```cpp
~SparseArray() =default
```


### function operator=

```cpp
inline SparseArray & operator=(
    SparseArray const & other
)
```


**Parameters**: 

  * **other** The [SparseArray](Classes/classecs_1_1_sparse_array.md) you want to copy 


**Return**: The Sparse array present in the class at the moment 

Operator copy of the [SparseArray](Classes/classecs_1_1_sparse_array.md) class 


### function operator=

```cpp
inline SparseArray & operator=(
    SparseArray && other
)
```


**Parameters**: 

  * **other** The [SparseArray](Classes/classecs_1_1_sparse_array.md) you want to move 


**Return**: The Sparse array present in the class at the moment 

Operator move of the [SparseArray](Classes/classecs_1_1_sparse_array.md) class 


### function operator[]

```cpp
inline referenceType operator[](
    size_t idx
)
```


### function operator[]

```cpp
inline constReferenceType operator[](
    size_t idx
) const
```


### function begin

```cpp
inline iterator begin()
```


### function begin

```cpp
inline constIterator begin() const
```


### function cBegin

```cpp
inline constIterator cBegin() const
```


### function end

```cpp
inline iterator end()
```


### function end

```cpp
inline constIterator end() const
```


### function cEnd

```cpp
inline constIterator cEnd() const
```


### function size

```cpp
inline sizeType size() const
```


### function insertAt

```cpp
inline referenceType insertAt(
    sizeType pos,
    Component const & c
)
```


### function insertAt

```cpp
inline referenceType insertAt(
    sizeType pos,
    Component && c
)
```


### function emplaceAt

```cpp
template <class... Params>
inline referenceType emplaceAt(
    sizeType pos,
    Params &&... args
)
```


### function erase

```cpp
inline void erase(
    sizeType pos
)
```


### function getIndex

```cpp
inline sizeType getIndex(
    valueType const & c
) const
```


**Parameters**: 

  * **c** The std::optional<Component>, type of the component you want the index 


**Return**: The sizeType of the valueType's index you are looking for 

This function is used to get the index of the std::optional<Component> of the std::vector<std::optional<Component>> _data according to the given valueType (std::optional<Component>) 


-------------------------------

Updated on 2022-11-13 at 17:21:37 +0100