---
title: Function
index: 6
---

## Introduction

- reusable part of code
- takes input and gives output



## Function

- no variable number of arguments, no rest parameters, no default values
- can pass as value, e.g. assign to variable, return from function
- can't close over outer-scope variables
- obligatory type annotations for arguments and return type since can't infert
?? parameters are just variables that get assigned the arguments



## Closure

- anonymous function expression
- can pass as value, e.g. assign to variable, return from function
- can close over variables of outer scope
- captures outer variables either using immutable borrow, mutable borrow, or by taking ownership
- beware: can run only once if takes ownership of outer variables, since variables are owned and therefore dropped after first call!
- beware: all captured variables have same ownership, e.g. can't borrow one immutably but other mutably, etc.!
- can think of outer variables like invisible function parameters
- more overhead than function because of closure
- three types depending on ownership of captured variables
  - `Fn`: captured variables are borrowed immutably
  - `FnMut`: captured variables are borrowed mutably
  - `FnOnce`: captured variables are taken by ownership
- infers types from first usage, no obligatory type annotations
- can force `FnOnce` using `move` keyword, e.g. when passing to another thread 
