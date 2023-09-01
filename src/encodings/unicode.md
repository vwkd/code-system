# Unicode



## Introduction

- universal character encoding standard
- single character set, includes every character, superset of all other character sets
- multiple character encodings
- allows multi-lingual text
- no need for conversion of different encodings anymore
- Unicode all the things!



## Coded character set

- code space until about 1 million
- currently about 150,000 (10%) characters assigned, grows constantly
- divided in 17 planes of fixed size 2^16 (65,536, 16^4)
- 0th plane is Basic Multilingual Plane (BMP), contains most commonly-used characters
- character in BMP is notated by `U+XXXX`, where `XXXX` is the code point in hexadecimal, e.g. `A` is `U+0041`
- 1-16 higher planes are supplementary planes
- character in supplementary planes needs more than 4 hexadecimal digits to be represented, i.e. `U+XXXXX` or `U+XXXXXX`
- plane divided into block of no fixed size
- beware: character not necessarily _perceived character_, since might be made up of multiple characters, e.g. accents, emoji, etc. ⚠️
- beware: character can have duplicates, since one _perceived character_ could be made of different combinations of characters, e.g. diaeresis, etc. ⚠️
- beware: code point not necessarily character, since might not be assigned ⚠️
- beware: indexing code space usually doesn't make sense, since not necessarily actual character ❗️



## Encodings

- surrogate is a code point reserved for UTF-16
- scalar value is a code point except a surrogate, for UTF-8 and UTF-32

### UTF-8

- de facto standard
- backwards compatible with ASCII, ASCII characters have identical binary value, ASCII encoded text is valid UTF-8 encoded text
- variable-width
- 1, 2, 3 or 4 bytes
- byte of single-byte code point doesn't have high bit set, ASCII
- bytes of multibyte code point have high bit set, non-ASCII
- first byte of multibyte code point starts with as many `1`s as number of bytes
- following bytes of multibyte code point each start with `10`
- no bytes of code point is subslice of bytes of other code point
- no subslice of bytes of multibyte code point is valid bytes of code point
- knows if between code points or in middle of code point, e.g. if encoded text is cut off
- can think of blind sequence of single bytes, only reader groups some together and ends up with shorter sequence of characters
- advantage needs less space
- drawback can't index by code point, needs to read from start, linear time

### UTF-16

- variable-width
- 2 or 4 bytes
- "worst of both worlds"

### UTF-32

- fixed-width
- 4 bytes
- advantage can index by code point, constant time
- drawback needs more space, wastes 4 bytes for every character



## Resources

- [Wikipedia - Variable-width encoding](https://en.m.wikipedia.org/wiki/Variable-width_encoding)
- [Manish Goregaokar - Let's Stop Ascribing Meaning to Code Points](https://manishearth.github.io/blog/2017/01/14/stop-ascribing-meaning-to-unicode-code-points/)
