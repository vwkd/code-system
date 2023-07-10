---
title: String
index: 4
---

## Introduction

- list of UTF-8 encoded bytes, variable width encoding, character is 1-4 bytes long
- more complicated, but more correct
- can not be indexed, because one byte could be part of a multi-byte character
- beware: `.chars()` gets scalar values, not grapheme clusters, one grapheme cluster might have multiple scalar values, can use external `unicode-segmentation` crate



## `String`

- heap-allocated growable owned
- UTF-8 encoding
- like `Vec<u8>` but always valid UTF-8

?? is already a pointer to data on the heap
?? every heap-allocated data type is a pointer to a value on the heap
reference is a pointer to a pointer
avoid extra layers of indirection, e.g. pointer to pointer to pointer...
function argument type should be coercion target, e.g. `&str` instead of `&String`, slice instead of array or vector

implements deref trait to str



## `&str`

- string slice for some string in memory
- string not necessarily heap, can be in binary as well
- can only use reference directly since size is not known at compile-time for stack
- `&String` gets automatically coerced to `&str`
reference to string can get coerced to string slice
- have static lifetime

dynamically sized type



## String literal

- stored in binary directly
- string slice pointing to address in binary
