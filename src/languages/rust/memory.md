---
title: Memory
index: 3
---

## Introduction

- uses ownership based resource management
- no manual memory management, no garbage collection
- more constrained, but can use `unsafe` to manage manually



## Ownership

- each value has a variable that's its owner
- there can only be one owner at a time
- if the owner goes out of scope, the value is dropped
- checked at compile time

who is responsible for clean up
can use shared pointer for shared ownership???

move semantics by default, implicit, by assigning ??



## Borrowing rules

- can either have one mutable reference or any number of immutable references
-> prevents data races
- references must always be valid
-> prevents null pointers



## Interior Mutability
??? misleading name referring to implementation (declaration of variable)

pattern that allows to mutate value even while immutable references exists
usually disallowed by borrowing rules

for certain memory safe scenarios
more expanded borrowing rules
but can't verify statically

checks expanded borrowing rules dynamically at runtime
not statically at compile time



## Variable

- container of data, points to area in memory, on stack or on heap
- called "pointer" if data is on heap??
- stored itself on stack
- all data in memory is owned by single variable, not multiple
- memory is dropped when variable goes out of scope, like usual for stack, deallocated on heap

- lifetime is its scope, region of code where it's valid
- on assignment or function call copies variable
  - for primitive value (type that implement `Copy` trait) copies value, "pass by value"
  - beware: also in smart pointer initialization function, e.g. `Box::new(42)`
  - for heap-allocated value copies pointer, transfers ownership to new variable, old variable is invalidated, "moved", "pass by reference"
  ?? also moves structs even though on stack??
- beware: variable is always copied, but underlying data only if not on heap!
- can clone data instead using `.clone()` method
?? to copy instead of move
- return value of function moves ownership to callsite



## move

copy of data from one binding to another
invalidates the previous owner

guaranteed to be bitwise copy of the data contained in the type, equivalent to a memcpy of the appropriate size

implicit during binding

implementing Copy trait does not invalidate the prior owner,



## Dropping

drops variable at end of scope
in reverse order of creation, i.e. LIFO

calls `drop` method from Drop trait
disallows call manually, automatic call would potentially double free

Can instead call `drop` function from std
included in prelude, no need to bring it into scope
is empty function that simply takes ownership such that drops at end



## Unsafe

opt out of some safety guarantees
static analysis is restrictive, can be memory safe but not statically analizable
borrowing rules are still checked??

can easily identify potential problematic section in code

can dereference raw pointer
can call unsafe function or method
can access or modify mutable static variable
can implement unsafe trait
can access field of union

unsafe block may be inside safe function, if creates safe abstraction around unsafe code





## Resources

- [Richard Feldman - The Rust Programming Language](https://frontendmasters.com/courses/rust/)
- [Ryan Levick - Introduction to Rust Part 1](https://youtube.com/watch?v=WnWGO-tLtLA) and [Ryan Levick - Introduction to Rust Part 2](https://youtube.com/watch?v=lLWchWTUFOQ)
- [Ryan Levick - Rust Stream: Iterators](https://youtube.com/watch?v=7I11degAElQ)
- [fasterthanlime - Self-referential structs (in Rust)](https://youtube.com/watch?v=xNrglKGi-7o)
- [Let's Get Rusty - Understanding Ownership in Rust](https://youtube.com/watch?v=VFIOSWy93H0&list=PLai5B987bZ9CoVR-QEIN9foz4QCJ0H2Y8&index=4)
