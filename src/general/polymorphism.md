# Polymorphism



## Introduction

- ability of identifier to represent multiple concrete data types
- specifies base type, can use common functionality of base type, abstracts over concrete types
- e.g. call method on composite type without knowing which concrete type it is
- generates multiple implementations, one for each concrete type ("monomorphization")
- can be static or dynamic
- allows extendable types
- allows single implementation
- also calls generic data type



## Static

- implementation for type is selected at compile time
- can think of duplicating code for each concrete type
- needs static type information
- no performance penalty
- increased binary size due to duplication of generated code



## Dynamic

- implementation for type is selected at runtime
- doesn't need static type information
- performance penalty due to extra lookup during runtime
- no binary size increase
<!-- todo: when is the specific implementation for each concrete type generated? if at compile time, why doesn't it similarly increase binary size like static dispatch? -->



## Dispatch

- process of selecting implementation for type



## Resources

- Wikipedia
