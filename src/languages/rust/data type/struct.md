---
title: Struct
index: 5
---

## Introduction

- grouping of related variables (fields) and functions (methods)
- no inheritance
- separate `impl` block for methods, multiple
- `self` as first argument for instance method, otherwise associated function of struct type itself
- uses single dot to access struct members, uses double colon to access associated functions

Product type, bundles multiple types together

also called a "type", even though there can be other types like enums
likely because it's the only type that can customize ??



## Ownership

- assigning of non-primitive struct property moves it



## Instantiation

- define fields in any order
- single name shorthand for fields of same name as variable, adapted from JavaScript
- spread syntax shorthand for reusing remaining fields from existing struct, adapted from JavaScript

must define all fields
if has private fields and imports strict in other module, can't instantiate it
implement associated function `new` that creates new instance, can initializes private fields
??? Same for enum




## Tuple Structs

- without named fields
- use as a named tuple, can distinguish from other (named) tuples
- is also constructor function for itself, e.g. `Foo` is like closure `|v| Foo(v)`

```rs
struct Foo(u8);

let v = [1, 2, 3];
let w = v.map(Foo);
```



## ?? State based implementations

model state and offer different methods based on state

use generics and zero-sized types
use unit structs for states

add generic parameter to struct for state, can default it to one of the states

must use generic parameter in field
if doesn't want to use it, can use zero-sized type PhantomData to "fake" using it, is optimized away at compile time

creates two distinct types from single struct, no duplication necessary
can now have different implementations

e.g. locked and unlocked password manager