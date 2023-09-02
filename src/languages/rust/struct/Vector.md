# Vector



## Introduction

can think of dynamic array

- smart pointer
- collection type
- sequence of values
- dynamic length
- same type
- for different types can use enum with attached values of different types
- iterable
- beware: wants to iterate over reference, otherwise moves elements into loop variable and can't use vector afterwards ❗️
- index can be dynamic
- beware: direct index copies element, must use reference for heap-allocated data type since move is not possible ❗️
- beware: can't access elements and also mutate collection, would be two borrows where at least one is mutable ❗️

reference to vector of Type can be coerced to reference to slice of Type ??? Or only of trait objects

implements `Deref<[T]>`

- in standard library
- automatically imported because included in prelude

?? takes ownership of its elements

always use &[T] instead of &Vec<T>

doubles it's current capacity each time that allocates
exponential

don't call `reserve_exact()` in a loop, thwarts exponential growth to linear growth
instead use `reserve()`, maintains exponential growth
or use `extend()` which preallocates under the hood

use Arc<[T]> over Vec<T> for sequence of data that's never mutated and cloned around often
use Rc if doesn't need multi-thread safety
use Box if never clones
e.g. hash map keys, etc.

Arc
has cheap constant time clone
doesn't need capacity field since can't mutate
also implements `Deref<[T]>` like `Vec<T>`
-> can replace Vec<T> if doesn't need mutation

Vec for modifying collection
don't use if doesn't modify
in other words: immutable Vec doesn't make sense !

if doesn't need to clone use Box<T>
stores heap data
is struct with pointer to heap data and length
if type is Sized then only pointer, no length
even more efficient than Arc
but clone would deep copy
can think of immutable Vec<T> without capacity

but use reference when doesn't need to give ownership
if there's an obvious owner that outlives the rest


## Construction

- can use `new` constructor function
- can't add elements because function can't accept variable number of arguments
- needs to call `push`
- can use `vec!` macro
- can add elements since macro supports variable number of arguments



## Accessor

- can use bracket notation
- panics if index is invalid
- can't access non-`Copy` element without reference, because would move out, leave invalid vector with "gap"
- instead can move out element with `remove` method, shifts all following elements to left
- can use `get` method
- returns `Option` with reference to element, won't panic, won't move out



## Resources

[Logan Smith - Use Arc Instead of Vec](https://youtube.com/watch?v=A4cKi7PTJSs)
[Logan Smith - The Dark Side of .reserve()](https://youtube.com/watch?v=algDLvbl1YY)
