# Character



## Introduction

- scalar type
- Unicode character
- beware: Unicode character is not necessarily actual character, see Unicode ⚠️
- Unicode scalar value
- fixed size, 4 bytes
- can think of `u32` without illegal numbers
- can think of UTF-32 string of length 1
- beware: `Vec<char>` is usually larger than equivalent `String` of same characters, since UTF-32 instead of UTF-8 ❗️
- `char`



## Resources
