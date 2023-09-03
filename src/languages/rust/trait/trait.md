---
title: Trait
index: 11
---

## Introduction

- set of functionality
- can implement for algebraic data type
- can have methods, associated functions, associated types, associated constants
- beware: no struct fields ❗️
- can instead move shared fields out into shared struct and use that in single field
- allows shared behavior
- enables polymorphism
- replaces interfaces and inheritance in other languages
- convention is to name after capitalized verb, e.g. `Clone`, `Copy`
- can think of as adjective, e.g. copyable, clonable, etc.
- called marker if empty, used only as label

it's also a type
dynamically sized

Self
implicit type parameter of trait
type that is implemented on
can think of pseudo syntax `impl MyTrait<MyStruct> {..}`
Self is by default unsized, Self: ?Sized
default trait methods can't return Self by value or take it as a parameter by value
needs either to specify that Self must be sized by default `trait MyTrait: Sized { ... }`
or that a method can only be called if Self is sized

most operators are implemented through traits



## Declaration

- defines signatures
- can use `Self` as alias for concrete type that implements trait
- optionally can provide default implementation
- beware: implementation can always overwrite default implementation ❗️
- beware: method with default implementation can call method without, needs to implement that one then ❗️
- can use generics and associated types



## Implementation

- type can implement multiple traits
- allows flexible composition, no hierarchies
- traits can overlap, e.g. one generic implementation, one for some trait bound, etc.
- ?? beware: duck typing, can implement more traits, can't prevent only some but not others ❗️

- if trait has method or associated function with same name as own, calls own by default
- to call method of trait can use explicit syntax `MyTrait::my_method(MyStruct, ...)`
- to call associated function of trait can use explicit syntax `<MyStruct as MyTrait>::my_function(...)`
- ?? if two traits have method or associated function with same name doesn't call any one by default, needs to use explicit syntax

- can implement trait on type
- enables extendable types
- can't implement trait on type if both trait and type are foreign, "orphan rule"
- to implement foreign trait on foreign type can create own wrapper type that implements foreign trait, e.g. tuple struct
- to access methods from original type can either implement desired methods manually on wrapper type or implement deref trait on wrapper type to access all
- can derive standard implementation using `derive` attribute if trait has associated derive macro
- specifies concrete types for generics and associated types

### Generic

- multiple implementations of trait for type
- for multiple concrete generic types
- specifies in `impl` header
- needs extra type annotations to distinguish multiple concrete generic types
- can think of generic type as input
- specified by user of type

### Associated type

- only one implementation of trait for type
- for single concrete associated type
- specifies in `impl` block
e.g. can dereference smart pointer only to a single other type
- no extra type annotations
- can think of associated type as output
- specified by type itself

### GAT

- like associate type, but
- can use trait method parameter types and lifetimes
- can think of mix of generic and associated type



## Supertrait

- trait that a trait requires being also implemented
- type that implements trait must also implement supertrait
- allows to depend on other traits
- can specify multiple
- syntax is like trait bound on name, multiple separated by plus



## Blanket Imlementations

- can implement trait for a generic type that satisfies a trait bound



## ?? generic type parameter

??
 
can specify default concrete type
implementation needs to specify concrete type only if different from default

useful in operator overloading



## ?? Operator overloading

customize behavior of operator

possible for operators that have associated traits in standard library ops module

eg Add operator



## Extension trait

idiomatic way to extend foreign trait

trait with bound ??
blanket implementation for all types

```rs
pub trait IteratorExt: Iterator { .. }

impl<T: Iterator> IteratorExt for T { .. }
```



## Resources

- [Stack Overflow - Why is the `Sized` bound necessary in this trait?](https://stackoverflow.com/a/30941589/2607891)
