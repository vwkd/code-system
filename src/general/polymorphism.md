# Polymorphism



## Introduction

- ability of identifier to represent subtypes
- specifies supertype, can use common functionality of supertype, abstracts over subtypes
- e.g. call method on composite type without knowing which concrete type it is
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



## Dynamic

- implementation for subtype is selected at runtime
- generates vtable with pointer to functionality for each subtype
- doesn't need static type information
- performance penalty at runtime, since extra lookup
- no binary size increase, since doesn't generate multiple implementations



## Dispatch

- process of selecting implementation for subtype



## Resources

- Wikipedia
