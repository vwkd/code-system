# Polymorphism



## Introduction

- ability of function to accept multiple different types in argument
- specifies common base type, can use common functionality of base type
- abstracts over concrete types
- allows extendable types
- allows single implementation
- multiple implementations are created, one for each concrete type
- static or dynamic is time when implementation is selected for type
- beware: probably more general, here restricts to functions ❗️
- also called generic function



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



## Monomorphism

- opposite of polymorphism
- also called specialized function

### Monomorphization

- generation of monomorphic functions from polymorphic function



## Resources

- Wikipedia
