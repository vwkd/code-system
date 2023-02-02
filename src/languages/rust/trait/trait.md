---
title: Trait
index: 7
---

## Introduction

- shared method signatures and optionally default implementations for structs
- set of functionality
- like interfaces
- beware: not for field!
- beware: method with default implementation can call method without, needs to implement that one then!
- beware: duck typing, can have more traits, can't specify only this but not other traits!??
- struct can implement multiple traits, can overlap, e.g. one generic implementation, one for some trait bound, etc.

## Trait Bound

- generic function parameter or return type which implements a trait, "bounded"
- can use multiple
- after generic type after colon, separated by plus
- alternatively using `where` clause after return type to make function signature more readable
- syntax sugar using `impl` directly, but can't specify same type for multiple arguments or return type, for return type can't return different types conditionally from function body

## Blanket Imlementations

- can implement trait for a generic type that satisfies a trait bound
