---
title: Struct
index: 5
---

## Introduction

- product type
- members can be fields and methods
- no inheritance
- replaces objects, classes in other languages
- can be concrete or generic
- uses static polymorphism

- itself stored on stack
- can store members on heap by allocating in implementation block and storing reference in member
- beware: type itself never stored on the heap, can only allocate in implementation ⚠️
- beware: often refers to type itself being stored on heap ⚠️
- all fields must be statically sized



## Declaration

?? can have one DST in last field
?? beware: not multiple ❗️

- can have methods in separate `impl` block
- can have multiple `impl` blocks
- by default is associated function on struct type
- if first argument is `self` is instance method
- `self` can be owned, immutable reference or mutable reference
- beware: methods can always mutate fields, independent if struct variable is mutable ❗️
- can use owned to return new type, and prevent old to be used afterwards
- can use associate function for custom constructor, by convention called `new`, can e.g. set default values, do calculations, etc.
- can use `Self` as alias for type, doesn't need to rename when renamed type



## Instantiation

- syntax is struct type followed by block with fields
- can define fields in any order
- single name shorthand for fields of same name as variable, like in JavaScript
- spread syntax shorthand for reusing remaining fields from existing struct, like in JavaScript
- can declare mutable, then can mutate all fields
- beware: can't control which fields are mutable, instead use setter methods ❗️

must define all fields
if has private fields and imports strict in other module, can't instantiate it
implement associated function `new` that creates new instance, can initializes private fields
??? Same for enum



## Access

- single dot on instance accesses members
- double colon on struct type accesses associated functions
- derivation of field like for variable, see Memory#Derivation
- beware: assigning of field that's not `Copy` moves it ❗️



## Tuple Structs

- like struct, but fields like tuple members without names
- use as a named tuple, can distinguish from other (named) tuples
- is also constructor function for itself, e.g. `Age` is like closure `|age| Age(age)`

```rs
struct Age(u8);

let ages = [21, 42, 84].map(Age);
```


## Unit struct

- empty struct
?? can use to implement trait on something without storing data inside it



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