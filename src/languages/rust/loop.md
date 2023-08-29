---
title: Loop
index: ???
---



## Introduction

???
- repeating part of code
- can break with `break` statement, can return value, defaults to unit
- can label ancestor loop, identifier must start with tick, can break out of ancestors loop using label



## for loop

- loop through collection
irrefutable pattern

- just sugar for iteration
- plain identifier uses `.into_iter()`
- beware: default is to consume collection ❗️
- `&` identifier uses `.iter()`
- `&mut` identifier uses `.iter_mut()`
- loops until iterator returns `None`
- can think of `while let Some(myvalue) = myiterator.next() { ... }`



## while loop



## `while let`

ir/refutable pattern
but warning if irrefutable since wouldn't need it

- loop as long as one value
pattern matches
