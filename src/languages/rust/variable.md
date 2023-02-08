---
title: Variable
index: 2
---

## Introduction

- points to area in memory
?? if writes to variable, changes variable to point to new address in memory or overwrites data at address in memory

- can be shadowed
- value can be computed expression
- type is inferred where possible
- can not be declared in global scope
- identifier uses snake case by convention



## Mutability

- immutable by default, opt-in to mutability, not other way around
- (im)mutability propagates deeply, e.g. tuples, arrays, vectors, structs, etc.
- can't define only certain part of type mutable, only all or nothing, e.g. one field of struct
- can use `_` to ignore assignment, doesn't move value, e.g. in destructuring
- can move mutable variable into immutable variable to freeze it again



### Constants

- can't be shadowed
- value can only be constant expression, not computed, i.e. also not mutable
- type needs to be specified
- can be declared in any scope, including global scope
- identifier uses upper case by convention
