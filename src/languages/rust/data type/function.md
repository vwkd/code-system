---
title: Function
index: 6
---

## Introduction

- is expression, can pass as value, e.g. assign to variable, return from function
- can't close over outer-scope variables
- can be concrete or generic
- uses static polymorphism



## Declaration

- no variable number of arguments, no rest parameters, no default values
- parameter takes irrefutable pattern
- obligatory type annotations for arguments and return type since can't infer
- immutable parameters by default, can declare mutable
- returns unit by default implicitly if doesn't return a value
- returns implicitly last expression if any
- can return early with `return` statement



## Function Pointer

??

can pass functions as values
e.g. in `map` method

beware: lowercase
implements all three closure traits

? instead of using closure as trait bound

best practice to accept closure in argument, can pass function pointer or closure