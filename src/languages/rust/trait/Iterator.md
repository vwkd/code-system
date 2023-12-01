# Iterator



## Introduction

- ability to iterate over type
- provides common interface for iteration
- abstracts away over concrete implementation of iteration
- zero-cost abstraction, no runtime overhead
- lazy evaluation



## Implementation

- usually implements on wrapper type
- allows to separate iterator state from value
- allows contained value to be immutable
- can make wrapping type transparent by implementing `IntoIterator` for contained type, `into_iter` method returns wrapping type
- only needs to implement `next` method and associated type
- other methods have default implementation
- `Item` associated type is type that's iterated over
- `next` method returns `Some(Item)`, changes internal state of iteration, if at end returns `None`
- beware: may resume iteration again after end ❗️
- note: by default also implements `IntoIterator` that returns itself



## Usage

- usually type implements `IntoIterator`
- usually type also implements methods `iter()`/ `iter_mut()`
- usually type also implements `IntoIterator` for im/mutable reference that calls `iter()`/ `iter_mut()`

### `iter()`

- get iterator over immutable reference to values
- beware: name convention, only used in for loop ❗️

### `iter_mut()`

- get iterator over mutable reference to values
- beware: name convention, only used in for loop ❗️
- doesn't implement if mutation doesn't make sense, e.g. `HashSet`



## Adaptor

- method that returns another iterator
- before consumer
- can chain multiple
- doesn't evaluate since lazy

### `map`

### `filter`



## Consumer

- method that returns other type
- after adaptors
- can use only one
- starts evaluation

### `next`

- get next value in iteration
- iterator variable needs to be mutable because changes internal state of iteration
- used by other consumers under the hood

### `collect`

### `sum`

### `eq`

- compares iterators of same type
- is compared element-wise
- no need to collect into `Vec` to compare



## Resources

- [Jon Gjengset - Crust of Rust: Iterators](https://youtube.com/watch?v=yozQ9C69pNs)
