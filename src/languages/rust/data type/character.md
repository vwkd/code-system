# Character



## Introduction

- scalar type
- Unicode scalar value, i.e. Unicode code point except surrogate code point
- beware: not necessarily actual character, since USV might not yet be assigned ⚠️
- beware: can't be every actual character, since might be more than one USV, e.g. accents, emojis, etc. ⚠️
- beware: can have duplicates, since real character might have more than one USV ⚠️
- fixed size, 4 bytes
- can think of `u32`
- effectively UTF-32 string of length 1
- beware: `Vec<char>` is larger than equivalent `String` of same characters, since UTF-32 instead of UTF-8 ❗️
- `char`



## Resources

- [Wikipedia - Variable-width encoding](https://en.m.wikipedia.org/wiki/Variable-width_encoding)
