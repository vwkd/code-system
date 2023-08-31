# Unicode



## Introduction

- one big coded character set to include all and every character on earth
- includes almost 138,000 characters as of May 2019 and grows constantly
- no need for any encoding conversion anymore, Unicode all the things!
- first 128 characters are same as ASCII
- beware: not a character encoding standard, just the coded character set ❗️
- many different character encodings can encode all Unicode characters, like UTF-8, UTF-16, UTF-32
- a character in Unicode is notated by `U+XXXX`, where `XXXX` is the code point in hexadecimal, e.g. `A` is `U+0041`
- Unicode characters are grouped in "planes" of 2^16 (65,536) code points, there are already multiple planes, since they come one after each other and are not yet full, some characters have code points larger than 16^4 (65,536), those need more than 4 hexadecimal digits to be represented, i.e. `U+XXXXX` or `U+XXXXXX`



### Character encodings

### UTF-8

- variable-length
- uses 1, 2, 3 or 4 bytes (= _8_, 16, 24, 32 bits) per character
- is the character encoding standard of the Web
- backwards compatible with ASCII, encodes first 128 characters with same binary values like ASCII, so ASCII encoded text is valid UTF-8 encoded text, vice versa since can use UTF-8 with most old programs and languages that expect ASCII, as long as no string manipulation (operation on character-level like slicing, trimming, counting) and just simple input and output no attention needed

### UTF-16

- variable-length
- uses 2 or 4 bytes (= _16_ or 32 bits) per character

### UTF-32

- fixed-length
- uses 4 bytes (= _32_ bits) per character
- even for most simple characters wastes 4 bytes



## Resources
