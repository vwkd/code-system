# Vector



## Introduction

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

- in standard library
- automatically imported because included in prelude

?? takes ownership of its elements



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
