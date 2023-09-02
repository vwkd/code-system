# Tuple



## Introduction

- composite collection type
- fixed-length sequence of values of different types
- statically sized
- empty is unit, like `void` in other languages



## Usage

- not iterable
- index can't be range
- index must be static
- beware: direct index copies element, instead can get reference using `get` method ❗️
- beware: must use reference for heap-allocated data type since move is not possible ❗️
- beware: can't access and also mutate elements, would be two borrows where at least one is mutable, e.g. `t.0; t.1 = 1;` ❗️



## Resources
