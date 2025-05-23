# Generic



## Introduction

- specifies any traits that subtype implements
- trait must be dyn-compatible



## Trait bound

- enables static polymorphism

- syntax is angle brackets containing generic name followed by colon and trait name, multiple traits separated by plus
- shorthand is `impl` followed by trait name, multiple traits separated by plus
- beware: can't reuse generic at multiple places ❗️



?? statically sized
?? --> not necessarily, can weaken using `?Sized`

- by default only for statically sized types
- implicitly has `Sized` trait bound
- can remove with special question mark prefix `?Sized`
- beware: opt-out instead of opt-in ❗️




## Trait object

- enables dynamic polymorphism
- dynamically sized
- can specify `Self: Sized` on associated functions or methods to exclude from trait object
- can specify `Self: Sized` on trait to prevent trait object

- beware: no longhand syntax ❗️
- shorthand is `dyn` followed by trait name, multiple traits separated by plus
- beware: can't reuse generic at multiple places ❗️


- beware: often uses "trait object" as synonym for "reference / smart pointer to trait object" ⚠️

- uses in library to avoid users having to specify generic
- uses in method instead of generic to make trait dyn-compatible

- can only specify auto traits as additional traits
e.g. `Send`, `Sync`, etc.
- beware: can't specify multiple custom traits ❗️
- can use empty wrapper trait that's supertrait of multiple traits instead

only for concrete specified generic or associated type of trait, because can't capture in vtable

- can use `Any` trait to emulate dynamic typing
recover type from unique type id

### vtable

- always includes `drop`, pointer to `drop` function of concrete subtype
- always includes size and alignment, passed to allocator, needed for deallocation



## Resources

- [Logan Smith - Two Ways To Do Dynamic Dispatch](https://youtube.com/watch?v=wU8hQvU8aKM)
- [Jon Gjengset - Crust of Rust: Dispatch and Fat Pointers](https://youtube.com/watch?v=xcygqF5LVmM)
