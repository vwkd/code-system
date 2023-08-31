# Array



## Introduction

fixed-size collection of contiguous elements in memory

- collection type
- sequence of values
- fixed length
statically sized
- same type, but for different types can use enum with attached values of different types
- iterable
- beware: wants to iterate over reference, otherwise moves elements into loop variable and can't use array afterwards ❗️
- index can be dynamic
- beware: direct index copies element, must use reference for heap-allocated data type since move is not possible ❗️
- beware: can't access elements and also mutate collection, would be two borrows where at least one is mutable, e.g. `v[0]; v.push(1);` ❗️

array can be coerced into slice

can index ranges



## Resources
