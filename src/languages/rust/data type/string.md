# String



## Introduction

- slice of string
- sequence of Unicode characters
- beware: Unicode character is not necessarily actual character, see Unicode ⚠️
- beware: not necessarily stored on heap, see String literal ❗️
- uses UTF-8
- can think of slice `[u8]` without illegal numbers
- beware: unlike `char` which uses UTF-32 ❗️
- beware: `[char]` is usually larger than equivalent `str` of same characters, since UTF-32 instead of UTF-8 ❗️
- beware: can't index, because variable-width encoding ❗️
- also called string slice
- beware: don't confuse with owned string `String` ⚠️
- `str`



## Usage

- `.chars()` gets characters
- beware: Unicode character is not necessarily actual character, see Unicode ⚠️
- can use external `unicode-segmentation` crate to get grapheme clusters



## Literal

- stored in binary, loaded in memory of binary
- has static lifetime



## Resources
