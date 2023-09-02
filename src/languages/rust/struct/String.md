# String



## Introduction

- scalar collection type
- smart pointer, stores values on heap
- variable-length sequence of Unicode characters
- can think of `Vec<u8>`, without illegal numbers
- `String` is to `str`, what `Vec<T>` is to `[T]`
- beware: `Vec<char>` is usually larger than equivalent `String` of same characters, since UTF-32 instead of UTF-8 ❗️
- also called owned string
- beware: don't confuse with string slice `str` ⚠️

// todo: copy from vector



## Resources
