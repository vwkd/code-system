---
title: Variable
index: 2
---

## Introduction

- can be shadowed
- value can be computed expression
- type is inferred where possible
- can not be declared in global scope
- identifier uses snake case by convention

declaration takes irrefutable pattern and expression

prefix variable with underscore if doesn't want to use
beware: still binds, might move value and can't use later
instead use underscore pattern, doesn't bind
e.g.
```rs
let x = Some(String::from("hi"));
if let Some(_y) = x {}
// x can't use here anymore
```



## Mutability

- immutable by default, opt-in to mutability, not other way around
- propagates deeply into composite type
- beware: can't control granularly, only all or nothing, e.g. one field of struct
- can use `_` to ignore assignment, doesn't move value, e.g. in destructuring
- can move mutable variable into immutable variable to freeze it again



### Constant

- value must be constant expression, computable at compile time
- beware: value can't be computed, e.g. mutable ❗️
- type needs to be specified
- can't be shadowed
- identifier uses upper case by convention
- can be declared in any scope, including global scope
- creates new instance of value every time is used, different memory address, think of value being inlined



## Static variable

global variables

- like constant, but
- can be mutable, but accessing and mutating only in unsafe block
- uses same instance every time is used, same memory address, single value
- can use for large amounts of data, needs single fixed memory address, or when needs interior mutability

must have static lifetime

access immutable is safe
accessing or modifying mutable static variable is unsafe
parallel access could lead to data race



## Lifetime

- non-lexical lifetime
- from creation until last use

### Static

- entire duration of program
- built-in
