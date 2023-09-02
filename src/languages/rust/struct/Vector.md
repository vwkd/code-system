# Vector



## Introduction

- composite collection type
- smart pointer, stores values on heap
- variable-length sequence of values of single type
- can think of dynamic array
- for different types can wrap in enum with attached values
- in standard library
- automatically imported because included in prelude
- implements `Deref<[T]>`, `&Vec<T>` coerces into `&[T]`
- best practice to use `&[T]` instead of `&Vec<T>`

use for modifying collection
don't use if doesn't modify
in other words: immutable Vec doesn't make sense !

 use reference when doesn't need to give ownership
if there's an obvious owner that outlives the rest

use Box<[T]> if never mutates and never clones
e.g. hash map keys, etc.

use Rc<[T]> if never mutates and clones around often
use Arc if needs multi-thread safety



## Storage

- allocates values on heap
- struct holds pointer to value, length and capacity
- doubles capacity each time that allocates, over-allocates
- exponential growth
- allocation on average constant time, since pays off over following insertions

mutable, dynamic length, can grow

collection data is item buffer on heap
over-allocates a bit

 struct stores pointer to collection data, length and capacity

clone allocates new memory, copies over items
linear time
no extra capacity
creates new struct and points at new item buffer

`clone()` copies heap-data, then new struct on stack
but doesn't over-allocate, capacity is same as length
linear time

indexing is constant time
push is constant time on average
pop is constant time

reallocation copies all existing elements
finds next place on heap with capacity free space

push and insert will (re)allocate if len == capacity

does not guarantee any particular growth strategy when reallocating
guarantees O(1) amortized push

best practice to specify capacity in advance if knows, with `with_capacity` constructor

If len == capacity, (as is the case for the vec! macro), then a Vec<T> can be converted to and from a Box<[T]> without reallocating or moving the elements
??? how

beware: don't call `reserve_exact()` in a loop, thwarts exponential growth to linear growth
instead use `reserve()`, maintains exponential growth
or use `extend()` which preallocates under the hood



## Construction

- can use `new` constructor function
- can't add elements because function can't accept variable number of arguments
- needs to call `push`
- can use `vec!` macro
- can add elements since macro supports variable number of arguments



## Accessing

- implements `Index` and `IndexMut`, can index using bracket notation
- panics if index is invalid
- beware: , see❗️
- can get reference using `get` method, returns `Option` with reference to element, won't panic, won't move out
- can move out element using `remove` method, shifts all following elements to left
- beware: can't access and also mutate elements, would be two borrows where at least one is mutable, e.g. `vec[0]; vec.push(1);` ❗️



## Iteration

- iterable
- beware: usually wants to iterate over reference, otherwise moves elements into loop variable and can't use `Vec` afterwards ❗️



## Resources

[Logan Smith - Use Arc Instead of Vec](https://youtube.com/watch?v=A4cKi7PTJSs)
[Logan Smith - The Dark Side of .reserve()](https://youtube.com/watch?v=algDLvbl1YY)
