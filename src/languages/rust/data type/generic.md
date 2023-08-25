# Generic



## Introduction

- abstract data type that resolves to concrete data type
- enables polymorphism



## Trait bound

- trait that generic type must implement
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
- can resolve to concrete type at runtime
- e.g. for return type of function can conditionally return different concrete type, generic collection over trait, etc.
- enables dynamic polymorphism
- syntax is following generic name and colon and `dyn`, multiple separated by plus
- shorthand without naming generic directly with `dyn MyTrait`, but can't reuse generic at multiple places
- must put behind some sort of reference, e.g. `Box`

?? Size of concrete type that implements trait isn't known at compile time, could be anything...



## Resources
