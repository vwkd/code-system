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

?? generics also enable polymorphism, reuse code for multiple types, abstracted over types

generics can be bound by traits, allows any type that implements trait

traits use static dispatch by default
-> efficient code generation

Static polymorphism using
generics and usually trait bounds

Dynamic polymorphism using
trait objects


dynamically sized type
? that's why trait object need to be behind pointer



## Declaration

- defines signatures
- can use `Self` as alias for concrete type that implements trait
- optionally can provide default implementation
- beware: implementation can always overwrite default implementation ❗️
- beware: method with default implementation can call method without, needs to implement that one then ❗️



## Implementation

- type can implement multiple traits
- allows flexible composition, no hierarchies
- traits can overlap, e.g. one generic implementation, one for some trait bound, etc.
- ?? beware: duck typing, can implement more traits, can't prevent only some but not others ❗️

- if trait has method or associated function with same name as own, calls own by default
- to call method of trait can use explicit syntax `MyTrait::my_method(MyStruct, ...)`
- to call associated function of trait can use explicit syntax `<MyStruct as MyTrait>::my_function(...)`
- ?? if two traits have method or associated function with same name doesn't call any one by default, needs to use explicit syntax

- can implement trait on type, except if both trait and type are foreign
- enables extendable types
- e.g. from standard library
- to implement foreign trait on foreign type can create own wrapper type that implements foreign trait
- to access methods from original type can either implement desired methods manually on wrapper type or implement deref trait on wrapper type to access all
- can derive standard implementation using `derive` attribute if trait has associated derive macro



## Supertrait

- trait that a trait requires being also implemented
- type that implements trait must also implement supertrait
- allows to depend on other traits
- can specify multiple
- syntax is like trait bound on name, multiple separated by plus



## Associated Type

? If the type acts as an input, it should be a generic type parameter
If it acts as an output, it should be an associated type

generics allow multiple implementations, associated types are specific
when wants only one implementation for any given type
? also don't need to specify generic when use concrete type

type placeholder of trait
can use in signatures of method definitions
concrete type specified in implementation
allows to define trait without knowing concrete types until implementation

using generics must annotate the types in each implementation
could have multiple implementations of trait for a type
trait can be implemented for a type multiple times, changing the concrete types of the generic type parameters each time
would have to provide type annotations when instances to indicate which implementation of trait wants to use

can’t implement a trait on a type multiple times
don’t need to annotate types

capture types that appear in methods but are determined based on the impl that is chosen (i.e., by the type implementing the trait) rather than being specified from the outside

////

placeholder type
methods can use it

unknown until implementation
concrete type specified at implementation

can have only one concrete type in all implementations
different from generic where can have multiple implementations for different concrete types

### GAT

generic associated types are an extension that permit associated types to have generic parameters.

allows associated types to capture types that may include generic parameters that came from a trait method
These can be lifetime or type parameters

Often, this occurs when the associated type wants to include data borrowed from self or some other parameter



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