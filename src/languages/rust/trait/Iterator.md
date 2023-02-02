---
title: Iterator
index: 12
---

## Introduction

- ?? thing that allows iteration
- makes data structure iterable

- data structure implements `Iterator` trait
- only needs to implement `next` method, rest have default implementation

- `iter()` gives immutable reference to values, `iter_mut()` gives mutable reference to values, `into_iter` gives owned values
- can get next value using `next()` method
- iterator is lazy, computes next value only when calls `next()`
- iterator variable needs to be mutable because `next()` changes internal state of iteration



## Usage

- can iterate over using `for .. in ..` loop
- adaptor methods return another iterator, e.g. `map`
- consumer methods return other type, e.g. `sum`, `collect`, etc.
 