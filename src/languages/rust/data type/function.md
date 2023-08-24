---
title: Function
index: 6
---

## Introduction

- is expression, can pass as value, e.g. assign to variable, return from function
- can't close over outer-scope variables
- can be concrete or generic
- uses static polymorphism

generic implicitly has Sized trait bound
generic by default only for statically sized types
can relax by prefixing with question mark ?Sized
parameter then needs to be some sort of pointer



## Declaration

- no variable number of arguments, no rest parameters, no default values
- parameter takes irrefutable pattern
- obligatory type annotations for arguments and return type since can't infer
- immutable parameters by default, can declare mutable
- returns unit by default implicitly if doesn't return a value
- returns implicitly last expression if any
- can return early with `return` statement



## Closure

- anonymous function expression
- can pass as value, e.g. assign to variable, return from function
- can close over variables of outer scope
- can think of outer variables like invisible function parameters
- input and output types are concrete, can't create one with generics
- beware: closure type definition can have generic input and output types, accepts any closure that satisfies them!
- infers input and output types from first usage, no obligatory type annotations
- captures outer variables either using immutable borrow, mutable borrow, or by taking ownership
- has type depending on ownership of captured variables
  - `Fn`: captured variables are borrowed immutably
  - `FnMut`: captured variables are borrowed mutably
  - `FnOnce`: captured variables are taken by ownership
- can create `FnOnce` using `move` keyword, e.g. when passing to another thread 
- beware: can run only once if takes ownership of outer variables, since variables are owned and therefore dropped after first call!
- beware: all captured variables have same ownership, e.g. can't borrow one immutably but other mutably, etc.!
- more overhead than function because of closure



## Function Pointer

??

can pass functions as values
e.g. in `map` method

beware: lowercase
implements all three closure traits

? instead of using closure as trait bound

best practice to accept closure in argument, can pass function pointer or closure