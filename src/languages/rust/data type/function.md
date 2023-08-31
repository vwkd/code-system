---
title: Function
index: 6
---

## Introduction

- expression
- can't close over outer-scope variables
- can be concrete or generic
- uses static polymorphism

- anonymous unique zero-sized type
- beware: can't specify concrete type, instead coerce to function pointer or closure ❗️
- implements the Fn\* traits
- coerces to function pointer
- beware: don't confuse with function pointer ❗️



## Declaration

- fixed number of arguments
- beware: no variable number of arguments, no rest parameters, no default values ❗️
- parameter takes irrefutable pattern
- obligatory type annotations for arguments and return type since can't infer
- immutable parameters by default, can declare mutable
- returns unit by default implicitly if doesn't return a value
- returns implicitly last expression if any
- can return early with `return` statement



## Resources

- [Logan Smith - Rust Functions Are Weird (But Be Glad)](https://youtube.com/watch?v=SqT5YglW3qU)
