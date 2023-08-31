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

? sequence of characters
? similar to `[char]`



## String slice

- `&str`
- slice of string
- dynamically sized type
- string not necessarily on heap, can be in binary as well
- `&String` gets automatically coerced to `&str`
reference to string can get coerced to string slice



## String literal

- is string slice
- has static lifetime
- string stored in binary, loaded in memory of binary