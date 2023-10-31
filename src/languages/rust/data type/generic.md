# Generic



## Introduction

- by default only for statically sized types
- implicitly has `Sized` trait bound
- can remove with special question mark prefix `?Sized`
- beware: opt-out instead of opt-in ❗️



## Trait bound

- trait that must implement
- restricts what generic type can be
- can specify multiple
- must resolve to concrete type at compile time
- beware: can't resolve to concrete type at runtime, instead use trait object ❗️
- enables static polymorphism
- syntax is following generic name and colon, multiple separated by plus
- shorthand without naming generic directly with `impl MyTrait`, but can't reuse generic at multiple places

can only do for object-safe traits
all methods on trait have no generic parameters and don't return self
? otherwise compile can't figure out concrete type



## Trait object

- like trait bound, but
- dynamically sized type
- can resolve to concrete type at runtime
- e.g. for return type of function can conditionally return different concrete type, generic collection over trait, etc.
- enables dynamic polymorphism
- syntax is following generic name and colon and `dyn`, multiple separated by plus
- shorthand without naming generic directly with `dyn MyTrait`, but can't reuse generic at multiple places

?? Size of concrete type that implements trait isn't known at compile time, could be anything...

- reference is fat pointer
- contains two pointers, to data and also to vtable

virtual method table
table of function pointers
map of method call names to function pointers
also called vtable
?? has pointers to all functions that struct?? implements
in static memory
generated at compile time

performance penalty
two pointer dereferences

- beware: often uses "trait object" as synonym for "reference / smart pointer to trait object" ⚠️



## Resources

- [Logan Smith - Two Ways To Do Dynamic Dispatch](https://youtube.com/watch?v=wU8hQvU8aKM)
