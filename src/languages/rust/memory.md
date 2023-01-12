---
title: Memory
index: 2
---

## Introduction

- using model of ownership
- no manual memory management, no garbage collection
- more constrained, but can use `unsafe` to manage manually

## Variable

- container of data, on stack or on heap, "pointer" to data on heap
- stored itself on stack
- all data in memory is owned by single variable, not multiple
- memory is dropped when variable goes out of scope, like usual for stack, deallocated on heap
- on assignment or function call copies variable
  - for primitive value (type that implement `Copy` trait) copies value, like pass by value
  - for heap-allocated value copies pointer, transfers ownership to new variable, old variable is invalidated, "moved", like pass by reference
- beware: variable is always copied, but underlying data only if not on heap!
- can clone data instead using `.clone()` method
- return value of function moves ownership to callsite

## Reference

- safe pointer to data in memory owned by existing variable, "borrow"
- beware: data can be on stack or heap, e.g. array, struct, the existing variable is always on heap
- tied to existing variable, must go out of scope before or at same time as existing variable, i.e. dangling pointer
- when it goes out of scope nothing happens
- scope is between declaration and last use, smaller than usual
- can have either multiple immutable references or single mutable reference in a scope, e.g. prevents data races
- can't use existing variable in meantime??

## Slice

- reference to part of a collection, e.g. array, vec, etc.
- can think of as view or window into data

## Resources

- [Richard Feldman - The Rust Programming Language](https://frontendmasters.com/courses/rust/)
- [Ryan Levick - Introduction to Rust Part 1](https://youtube.com/watch?v=WnWGO-tLtLA) and [Ryan Levick - Introduction to Rust Part 2](https://youtube.com/watch?v=lLWchWTUFOQ)
- [Ryan Levick - Rust Stream: Iterators](https://youtube.com/watch?v=7I11degAElQ)
- [fasterthanlime - Self-referential structs (in Rust)](https://youtube.com/watch?v=xNrglKGi-7o)
- [Let's Get Rusty - Understanding Ownership in Rust](https://youtube.com/watch?v=VFIOSWy93H0&list=PLai5B987bZ9CoVR-QEIN9foz4QCJ0H2Y8&index=4)