# Polymorphism



## Introduction

- ability of supertype to represent subtypes
- can use common functionality of supertype
- supertype abstracts over subtypes
- e.g. call method on composite type without knowing which concrete type it is
- beware: can think of type erasure, can't use individual functionality of subtypes anymore ❗️
- can be static or dynamic
- allows extendable types
- allows single implementation
- also calls generic data type



## Static

- implementation for subtype is selected at compile time
- generates implementation for each subtype ("monomorphization")
- can think of duplicating code for each subtype
- needs static type information
- no performance penalty at runtime
- increased binary size, since generates multiple implementations

- must resolve to concrete subtype at compile time
- beware: can't resolve to concrete type at runtime, instead use dynamic ❗️



## Dynamic

- implementation for subtype is selected at runtime
- uses vtable
- doesn't need static type information
- performance penalty at runtime, since extra lookup and less information for optimization
two pointer dereferences
- no binary size increase, since doesn't generate multiple implementations

- can resolve to concrete subtype at runtime
- e.g. conditionally return different concrete type in function, generic collection over supertype, etc.

- reference is fat pointer
fat pointer, pointer to data and pointer to vtable
- contains two pointers, to data and also to vtable

call is pseudo `my_reference.vtable.my_method(my_reference.pointer)`
works regardless of which type is passed in, indirect through vtable

### Virtual method table (vtable)

- function pointers to functionality of supertype on subtype
- generated for each subtype
- beware: not one for each instance of subtype, unlike static ❗️
- beware: don't confuse different vtables for different supertypes ❗️
- generated at compile time
- beware: don't confuse with duplicate implementation for each subtype in static polymorphism ❗️



## Dispatch

- process of selecting implementation for subtype



## Resources

- Wikipedia
