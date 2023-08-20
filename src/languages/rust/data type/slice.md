# Slice



## Introduction

- dynamically-sized view into collection of contiguous sequence of elements
- e.g. of array, of vector, of string, etc.
- can think of view or window into collection
- collection value can be anywhere, e.g. stack, heap, static memory
- dynamically-sized because length of sequence unknown at compile time
- beware: often uses "slice" as synonym for "reference to slice"!
- immutable
- syntax is trailing brackets containing range



## Reference

- fat pointer to value, contains address and size of value
- points to value directly
- still tied to existing variable
- fixed-sized, statically-sized
- beware: must use some sort of reference to slice to get statically-sized ❗️
- reference to owned type can be automatically coerced to reference of slice, e.g. `&String` to `&str`
