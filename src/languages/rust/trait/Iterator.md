# Iterator



## Introduction

- ability to iterate over type
- provides common interface for iteration
- abstracts away over concrete implementation of iteration
- zero-cost abstraction, no runtime overhead
- lazy evaluation
- calls type that implements it also "iterator"



## Implementation

- associated type `Item` is type that's iterated over
- beware: for collection is usually element type ❗️
- method `next()` returns optional next value `Some(Item)` and advances internal iteration state or `None` at end
- beware: may resume iteration again after end ❗️
- other methods have default implementation, doesn't need to implement
- usually implements on wrapper type
- allows to separate iterator state from value
- allows contained value to be immutable
- by convention calls wrapper type `IntoIter` over owned items, `Iter` over reference items, `IterMut` over mutable reference items
- automatically implements `IntoIterator` that returns itself

???? can make wrapper type transparent by implementing `IntoIterator` for contained type



## Adaptor

- method that returns another iterator
- before consumer
- can chain multiple
- doesn't evaluate, lazy

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
