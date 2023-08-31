# String



## Introduction

- sequence of Unicode scalar values
- collection type
- dynamically sized
- beware: not necessarily stored on heap, see String literal ❗️

- slice of string

- can think of slice `[u8]`
but only valid Unicode scalar values
but shorter actual string because some are grouped together
but valid UTF-8
- beware: can't index, because variable-width encoding ❗️

- also called string slice
- beware: don't confuse with owned string `String` ⚠️

- string not necessarily on heap, can be in binary as well

- `str`



## Usage

- `.chars()` gets characters
- beware: Unicode character is not necessarily actual character, see Unicode ⚠️
- can use external `unicode-segmentation` crate to get grapheme clusters



## String literal

- static lifetime
- string stored in binary, loaded in memory of binary



## Resources
