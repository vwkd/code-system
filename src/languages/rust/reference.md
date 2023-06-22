# Reference



## Introduction

- safe pointer to data in memory owned by existing variable, "borrow"
- beware: data can be on stack or heap, e.g. integer, array, struct
- points to variable (on stack), follows that variable to get to data
- lifetime must be smaller than variable it references, prevents dangling pointer
- when it goes out of scope nothing happens, data is not dropped
- scope is between declaration and last use, smaller than variable scope
- can have either multiple immutable references or single mutable reference in a scope, e.g. prevents data races
- can't use existing variable in meantime??



## Lifetime annotation

???
minimum lifetime
can assign any same type with longer lifetime
- minimum lifetime of input reference, maximum lifetime of output reference
- specified as another reference lifetime
- ??usually output reference lifetime 
- specifies minimum lifetime of output reference is at least lifetime of input reference, not exact same lifetime
- beware: doesn't change lifetime, just clarifies relationships!
- necessary when can't infer ("elide")
  - references in function return type with multiple references in function arguments
  - references in struct field and any implementations
- beware: only ever used on references!
- type of generic
- static lifetime is duration of whole program

