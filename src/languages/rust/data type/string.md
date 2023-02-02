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



## `&str`

- string slice for some string in memory
- string not necessarily heap, can be in binary as well
- can only use reference directly since size is not known at compile-time for stack
- `&String` gets automatically coerced to `&str`
- have static lifetime



## String literal

- stored in binary directly
- string slice pointing to address in binary
