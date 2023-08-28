---
title: Function
index: 6
---

## Introduction

- expression
- can pass as value
- e.g. assign to variable, pass to function, return from function
- can't close over outer-scope variables
- can be concrete or generic
- uses static polymorphism

- anonymous unique type
- beware: can't specify type, instead coerce to function points or closure ❗️
- zero-sized
- implements the Fn\* traits
- coerces to function pointer
- beware: don't confuse with function pointer ❗️



## Declaration

- no variable number of arguments, no rest parameters, no default values
- parameter takes irrefutable pattern
- obligatory type annotations for arguments and return type since can't infer
- immutable parameters by default, can declare mutable
- returns unit by default implicitly if doesn't return a value
- returns implicitly last expression if any
- can return early with `return` statement



## Function Pointer

- pointer to function
??? like reference to function, but ???
- can think of pointer to code instead of data
- implicit, doesn't have visible difference to function
- beware: can't create itself, instead get by casting function or closure that doesn’t capture variables ❗️
- can be called like function
- has static lifetime
- implements all three closure traits `Fn`, `FnMut`, `FnOnce`
- can pass in place of closure
- best practice to accept closure to be most general
- syntax is lowercase `fn`
- beware: don't confuse with closure ❗️
