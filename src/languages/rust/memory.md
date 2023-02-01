---
title: Memory
index: 2
---

## Introduction

- using model of ownership
- no manual memory management, no garbage collection
- more constrained, but can use `unsafe` to manage manually

## Variable

- container of data, points to area in memory, on stack or on heap
- called "pointer" if data is on heap??
- stored itself on stack
- all data in memory is owned by single variable, not multiple
- memory is dropped when variable goes out of scope, like usual for stack, deallocated on heap
- scope is also called "lifetime"??
- on assignment or function call copies variable
  - for primitive value (type that implement `Copy` trait) copies value, like pass by value
  - for heap-allocated value copies pointer, transfers ownership to new variable, old variable is invalidated, "moved", like pass by reference
  ?? also moves structs even though on stack??
- beware: variable is always copied, but underlying data only if not on heap!
- can clone data instead using `.clone()` method
- return value of function moves ownership to callsite

## Reference

- safe pointer to data in memory owned by existing variable, "borrow"
- beware: data can be on stack or heap, e.g. integer, array, struct
- points to variable (on stack), follows that variable to get to data
- lifetime must be smaller than variable it references, prevents dangling pointer
- when it goes out of scope nothing happens, data is not dropped
- scope is between declaration and last use, smaller than variable scope
- can have either multiple immutable references or single mutable reference in a scope, e.g. prevents data races
- can't use existing variable in meantime??

### Lifetime annotations

- specify relationship between lifetimes of references when can't infer ("elide")
- needed for references in function return type with multiple references in function arguments
- needed for references in struct field and any implementations
- specify minimum lifetime, not exact same lifetime
- beware: don't change lifetime, just clarify relationships!
- beware: only ever used on references!
- type of generic
- static lifetime is duration of whole program

## Slice

- reference to part of a collection, e.g. array, vec, etc.
- can think of as view or window into data
- points to data directly, but still tied to existing variable?!?

## Resources

- [Richard Feldman - The Rust Programming Language](https://frontendmasters.com/courses/rust/)
- [Ryan Levick - Introduction to Rust Part 1](https://youtube.com/watch?v=WnWGO-tLtLA) and [Ryan Levick - Introduction to Rust Part 2](https://youtube.com/watch?v=lLWchWTUFOQ)
- [Ryan Levick - Rust Stream: Iterators](https://youtube.com/watch?v=7I11degAElQ)
- [fasterthanlime - Self-referential structs (in Rust)](https://youtube.com/watch?v=xNrglKGi-7o)
- [Let's Get Rusty - Understanding Ownership in Rust](https://youtube.com/watch?v=VFIOSWy93H0&list=PLai5B987bZ9CoVR-QEIN9foz4QCJ0H2Y8&index=4)