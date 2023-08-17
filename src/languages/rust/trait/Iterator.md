---
title: Iterator
index: 12
---

## Introduction

? type that's iterable, allows iteration

- implements `Iterator` trait
- only needs to implement associated type and `next` method, rest have default implementation

- `iter()` gives immutable reference to values
- `iter_mut()` gives mutable reference to values
- `into_iter()` gives owned values
- beware: `into_iter()` consumes collection, data is then dropped, can't use again!
- can get next value using `next()` method
- iterator is lazy, computes next value only when calls `next()`
- iterator variable needs to be mutable because `next()` changes internal state of iteration

zero cost abstraction, no runtime overhead



## For loop

- can iterate over using for loop
- just sugar
- plain identifier sugar for `.into_iter()`
- `&` identifier sugar for `.iter()`
- `&mut` identifier sugar for `.iter_mut()`
- beware: default is to consume iterator!

for loop is equivalent to
`while let Some(myvalue) = myiterator.next() { ... }`



## Usage

- adaptor methods return another iterator, e.g. `map`, `filter`, etc.
- consumer methods return other type, e.g. `sum`, `collect`, etc.
- can chain multiple adaptor methods and then single consumer method
- beware: without consumer method doesn't do anything since is lazy!

`eq` method compares iterators of same type, is compared element-wise, no need to collect into `Vec` to compare
