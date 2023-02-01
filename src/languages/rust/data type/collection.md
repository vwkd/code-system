---
title: Collection
index: 6
---

## Introduction

- multiple values
- deeply mutable only if variable is mutable

## Tuple

- list of values
- fixed length
- different types
- not iterable
- index must be static

## Array

- list of values
- fixed length
- same type, but for different types can use enum with attached values of different types
- iterable
- beware: wants to iterate over reference, otherwise moves elements into loop variable and can't use array afterwards ❗️
- index can be dynamic
- beware: direct index copies element, must use reference for heap-allocated data type since move is not possible ❗️
- beware: can't access elements and also mutate collection, would be two borrows where at least one is mutable, e.g. `v[0]; v.push(1);` ❗️

## Vector

- list of values
- dynamic length
- same type, but for different types can use enum with attached values of different types
- iterable
- beware: wants to iterate over reference, otherwise moves elements into loop variable and can't use vector afterwards ❗️
- index can be dynamic
- beware: direct index copies element, must use reference for heap-allocated data type since move is not possible ❗️
- beware: can't access elements and also mutate collection, would be two borrows where at least one is mutable ❗️

## HashMap

- key-value pairs
- dynamic length
- different types, both key and values can be any type
- iterable
- beware: wants to iterate over reference, otherwise moves elements into loop variable and can't use map afterwards ❗️