# Vector



## Introduction

- list of values
- dynamic length
- same type, but for different types can use enum with attached values of different types
- iterable
- beware: wants to iterate over reference, otherwise moves elements into loop variable and can't use vector afterwards ❗️
- index can be dynamic
- beware: direct index copies element, must use reference for heap-allocated data type since move is not possible ❗️
- beware: can't access elements and also mutate collection, would be two borrows where at least one is mutable ❗️

reference to vector of Type can be coerced to reference to slice of Type ??? Or only of trait objects

- in standard library
- automatically imported because included in prelude



## Resources
