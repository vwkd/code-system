---
title: String
index: 4
---

## Introduction

- list of UTF-8 encoded bytes, variable-width encoding, character is 1-4 bytes long
- more complicated, but more correct
- can not be indexed, because one byte could be part of a multi-byte character
- beware: `.chars()` gets scalar values, not grapheme clusters, one grapheme cluster might have multiple scalar values, can use external `unicode-segmentation` crate
- multiple data types, `str`, `String`



## String slice

? sequence of characters
? similar to `[char]`
? doesn't have size

must put behind some sort of pointer, usually behind reference

- `&str`
- slice of string
- string not necessarily on heap, can be in binary as well
- can only use reference directly since size is not known at compile-time for stack
- `&String` gets automatically coerced to `&str`
reference to string can get coerced to string slice

dynamically sized type



## String literal

- is string slice
- has static lifetime
- string stored in binary, loaded in memory of binary