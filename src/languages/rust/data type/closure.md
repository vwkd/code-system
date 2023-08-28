# Closure



## Introduction

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



## Resources
