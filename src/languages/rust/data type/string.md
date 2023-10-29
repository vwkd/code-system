# String



## Introduction

- scalar collection type
- variable-length sequence of Unicode characters
- beware: Unicode character is not necessarily actual character, see Unicode ⚠️
- stored as UTF-8
- can think of slice `[u8]` without illegal numbers
- dynamically sized
- part of existing string value in memory, doesn't exist by itself
- can't create, only coerce from existing string, must be statically sized
- beware: existing string value can be anywhere, e.g. heap, static memory ❗️
- can think of view into existing string
- beware: `[char]` is usually larger than equivalent `str` of same characters, since UTF-32 instead of UTF-8 ❗️
- also called string slice
- beware: often uses "string slice" as synonym for "reference to string slice" ⚠️
- beware: don't confuse with owned string `String` ⚠️
- clone is expensive, linear time
- `str`
- syntax is trailing brackets containing range or `as_ref()` method
- beware: use array indexing to prevent temporary value from being dropped early ❗️



## Reference

- fat pointer, also holds length



## Literal

- reference with static lifetime
- existing string value in static memory



## Usage

- panics if index not on character boundary
- beware: don't index, doesn't make sense with variable-width encoding ⚠️
- `.chars()` gets characters
- `char_indices()` gets characters and indices
- beware: Unicode character is not necessarily actual character, see Unicode ⚠️
- can use external `unicode-segmentation` crate to get grapheme clusters



## Resources
