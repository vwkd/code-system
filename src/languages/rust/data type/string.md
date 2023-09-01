# String



## Introduction

- slice of Unicode characters
- beware: Unicode character is not necessarily actual character, see Unicode ⚠️
- beware: not necessarily stored on heap, see String literal ❗️
- stored as UTF-8
- can think of slice `[u8]` without illegal numbers
- beware: `[char]` is usually larger than equivalent `str` of same characters, since UTF-32 instead of UTF-8 ❗️
- also called string slice
- beware: don't confuse with owned string `String` ⚠️
- `str`



## Usage

- panics if index not on character boundary
- beware: don't index, doesn't make sense with variable-width encoding ⚠️
- `.chars()` gets characters
- `char_indices()` gets characters and indices
- beware: Unicode character is not necessarily actual character, see Unicode ⚠️
- can use external `unicode-segmentation` crate to get grapheme clusters



## Literal

- stored in binary, loaded in memory of binary
- has static lifetime



## Resources
