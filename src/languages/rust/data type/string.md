---
title: String
index: 4
---

## Introduction

- list of UTF-8 encoded bytes, variable width encoding, character is 1-4 bytes long
- more complicated, but more correct
- can not be indexed, because one byte could be part of a multi-byte character
- beware: `.chars()` gets scalar values, not grapheme clusters, one grapheme cluster might have multiple scalar values, can use external `unicode-segmentation` crate



## Owned string

? similar to `Vec<char>`

`String`

- heap-allocated growable owned
- UTF-8 encoding
- like `Vec<u8>` but always valid UTF-8

?? is already a pointer to data on the heap
?? every heap-allocated data type is a pointer to a value on the heap
reference is a pointer to a pointer
avoid extra layers of indirection, e.g. pointer to pointer to pointer...
function argument type should be coercion target, e.g. `&str` instead of `&String`, slice instead of array or vector

implements deref trait to str



## String slice

? sequence of characters
? similar to `[char]`
? doesn't have size

must put behind some sort of pointer, usually behind reference

`&str`

- string slice for some string in memory
- string not necessarily heap, can be in binary as well
- can only use reference directly since size is not known at compile-time for stack
- `&String` gets automatically coerced to `&str`
reference to string can get coerced to string slice

dynamically sized type



## String literal

string slice
has static lifetime
stored of binary, loaded in memory of binary