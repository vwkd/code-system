# Fn & FnMut & FnOnce



## Introduction

- ability to call
- special syntax with signature of input and output types
- implements always `FnOnce`, possibly also `Fn`, possibly also `FnMut`
- can think of ABI for function, doesn't know exactly what it is, can call as long as respects signature



## `Fn`

- immutably borrows captured variables
- can call more than once
- can coerce to function pointer
- also implements `FnOnce`



## `FnMut`

- mutably borrows captured variables
- can call more than once
- also implements `Fn` (and hence `FnOnce`)



## `FnOnce`

- takes ownership of captured variables
- captured variables are dropped after first call
- can call only once 
- e.g. when passing to another thread



## Resources
