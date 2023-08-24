# Polymorphism



## Introduction

- ability of composite data type to be used with multiple different types
- specifies base type, can use common functionality of base type, abstracts over concrete types
- generates multiple implementations, one for each concrete type ("monomorphization")
- static or dynamic is time when implementation is selected for type
- is called generic
- allows extendable types
- allows single implementation



## Static

- implementation for type is selected at compile time
- needs static type information
- no performance penalty
- increased binary size due to duplication of generated code



## Dynamic

- implementation for type is selected at runtime
- doesn't need static type information
- performance penalty due to extra lookup during runtime
- no binary size increase



## Dispatch

- process of selecting implementation for type



## Resources

- Wikipedia
