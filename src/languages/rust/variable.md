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
- propagates deeply into type
- beware: can't control granularly, only all or nothing, e.g. one field of struct
- can use `_` to ignore assignment, doesn't move value, e.g. in destructuring
- can move mutable variable into immutable variable to freeze it again



### Constant

- can't be shadowed
- value can only be constant expression, not computed, i.e. also not mutable
- type needs to be specified
- can be declared in any scope, including global scope
- identifier uses upper case by convention

?? variable memory address, might change
? can duplicate its data whenever used



## Static variable

global variables

like constant
must annotate type
identifier uses upper case by convention

must have static lifetime

but
fixed memory address, always same
can be mutable, but accessing and mutating only in unsafe block