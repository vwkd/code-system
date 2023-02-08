---
title: Iterator
index: 12
---

## Introduction

- ?? thing that allows iteration
- makes data structure iterable

- data structure implements `Iterator` trait
- only needs to implement associated type and `next` method, rest have default implementation

- `iter()` gives immutable reference to values, `iter_mut()` gives mutable reference to values, `into_iter()` gives owned values
- beware: `into_iter()` consumes collection, data is then dropped, can't use again!
- can get next value using `next()` method
- iterator is lazy, computes next value only when calls `next()`
- iterator variable needs to be mutable because `next()` changes internal state of iteration



## Usage

- can iterate over using for loop
- for loop just sugar, plain identifier for `into_iter()`, `&` identifier for `iter()`, `&mut` identifier for `iter_mut()`
- adaptor methods return another iterator, e.g. `map`, `filter`, etc.
- consumer methods return other type, e.g. `sum`, `collect`, etc.
- can chain multiple adaptor methods and then single consumer method
- beware: without consumer method doesn't do anything since is lazy!
