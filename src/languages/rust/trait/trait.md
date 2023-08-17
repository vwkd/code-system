---
title: Trait
index: 11
---

## Introduction

- shared method signatures and optionally default implementations for type
- set of functionality
- like interfaces
- beware: not for field!
- beware: method with default implementation can call method without, needs to implement that one then!
- beware: duck typing, can have more traits, can't specify only this but not other traits!??
- type can implement multiple traits, can overlap, e.g. one generic implementation, one for some trait bound, etc.

enables polymorphism
set of functions and methods that types can implement
Similar to interfaces in other languages

types can implement multiple traits
traits can have default implementations
-> more flexible code design, no hierarchies, composition

Extensions
trait can extend type outside of crate where was defined
-> extendable types
e.g. types in the standard library
but can't implement foreign trait on foreign type, would need to create own annoying wrapper type that implements foreign trait

?? generics also enable polymorphism, reuse code for multiple types, abstracted over types

generics can be bound by traits, allows any type that implements trait

traits use static dispatch by default
-> efficient code generation
???? What is static Dispatch

replace inheritance in other languages

Static polymorphism using
generics and usually trait bounds

Dynamic polymorphism using
trait objects

Self is concrete type that implements the trait

Can implement trait with methods that has same name as own method
To call method of trait needs to use explicit syntax `Trait::method(struct, ..)`

can implement two traits with same method name
?? which method is called by default ?? latest defined ??

can implement trait with same associated function as own
calls own by default
can call associated function of trait using extended syntax `<struct as Trait>::function(..)`

orphan rule
?? can only implement trait for type if trait or type is defined in own module, not if both are defined outside of module
e.g. can't implement trait from standard library for type from standard library, because both are defined outside module
can get around limitation by creating wrapping struct
To access methods from original type can either implement desired ones manually on wrapping struct or implement deref trait on wrapping struct to access all

dynamically sized type
? that's why trait object need to be behind pointer



## Trait Object


??? allows to treat different types that implement same trait as interchangeable

??? dynamic dispatch

?? allow to abstract over multiple types that share a common trait

?? Size of concrete type that implements trait isn't known at compile time, could be anything...

e.g. `dyn Animal`

?? can put behind reference
can use `Box` smart pointer
e.g. `Box<dyn Animal>`

??? Vector can't accept trait bound !?! Can make vector generic over trait only with dynamic polymorphism ?? Can make generic at all only using Dynamic polymorphism???
?? can use in vector
e.g. `Vec<Box<dyn Animal>>`

a pointer + dyn keyword + trait
pointer can be ??reference, Box


## Common traits

should implement on public types

### Debug

allows debug formatting
useful in print
can derive

### Clone

allows to copy type, with `clone()` method
can derive

### Default

allows to create instances with default values, with `default()` associated function
primitive types have default values, e.g. number is zero, string is empty
for enum needs to specify default variant with `#[default]`
can derive if all fields implement it too
custom implementation if wants to custom default values

### PartialEq

allows to compare instances of type, e.g. in `assert_eq!`
?? Only equality
can derive

### Send

type is safe to send between threads
automatically implemented, unless contains type that is not safe to send
e.g. if contains `Rc<..>`, could use `Arc<..>` instead

### Sync

type is safe to be shared between threads via references
automatically implemented, unless contains type that is not safe to sync

### PartialOrd

### Hash

### Eq

### Ord

### Serialize

allows to serialize in common formats
from serde crate
shouldn't implement by default, instead gate behind feature flag, can opt into dependency on serde

### Deserialize

allows to deserialize from common formats
from serde crate
shouldn't implement by default, instead gate behind feature flag, can opt into dependency on serde

### Deref & DerefMut

?? coerce to reference
allows to trat type the same as reference, use in same places, e.g. with dereference operator

opt in to coercion

associated type `target`
not a type parameter since each “smart pointer” should only ever be dereferenceable to a single other type

?? also customizes behavior of deference operator
allows to be used with dereference operator
because will coerce to reference which knows how to dereference

implicit deref coercion automagically
?? on function call
cascades until last, e.g. &Box<String> -> &String -> &str
for im/mutable reference of one type to immutable reference of other type, and for mutable to mutable

note: `.deref()` bad method name, because only converts to reference, the actual dereferencing is done in the deref coercion (regardless of Deref)

### Drop

?? specify what happens when owning variable goes out of scope

included in prelude, automatically in scope

### Sized

? implemented for statically sized types



## Trait Bound

// todo: move to function?

- generic function parameter or return type which implements a trait, "bounded"
- can use multiple
- after generic type after colon, separated by plus
- alternatively using `where` clause after return type to make function signature more readable
can specify same generic multiple times ?!?
- syntax sugar using `impl` directly, but can't specify same type for multiple arguments or return type, for return type can't return different types conditionally from function body

is limited to single type, can't mix multiple types that implement trait
use trait object instead to mix multiple types

can only do for object-safe traits
all methods on trait have no generic parameters and don't return self
? otherwise compile can't figure out concrete type



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



## Supertrait

?? other trait that trait depends on
struct that implement trait must also implement supertrait

?? can define it similar to trait bound after name
`trait MyTrait: SuperTrait { ... }`



## Extension trait

idiomatic way to extend foreign trait

trait with bound ??
blanket implementation for all types

```rs
pub trait IteratorExt: Iterator { .. }

impl<T: Iterator> IteratorExt for T { .. }
```