# Polymorphism



## Introduction

- ability of identifier to represent multiple concrete data types
- specifies base type, can use common functionality of base type, abstracts over concrete types
- e.g. call method on composite type without knowing which concrete type it is
- can be static or dynamic
- allows extendable types
- allows single implementation
- also calls generic data type



## Static

- implementation for concrete type is selected at compile time
- generates implementation for each concrete type ("monomorphization")
- can think of duplicating code for each concrete type
- needs static type information
- no performance penalty at runtime
- increased binary size, since generates multiple implementations



## Dynamic

- implementation for concrete type is selected at runtime
- generates vtable with pointer to functionality for each concrete type
- doesn't need static type information
- performance penalty at runtime, since extra lookup
- no binary size increase, since doesn't generate multiple implementations



## Dispatch

- process of selecting implementation for concrete type



## Resources

- Wikipedia
