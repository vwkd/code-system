# Character encoding



## Introduction

- computers can store only bits, "binary digits", 0 and 1
- to represent anything else like letters, numbers, symbols needs character encoding scheme
- everything, e.g. text, file, image, is encoded, there is nothing like "plain text", must always know the encoding standard used, otherwise the bits are useless
- seeing garbled text just means the wrong encoding was used when reading file, can decode only with proper encoding, unless if text is read using wrong encoding and then converted into another encoding, then information is lost unless exact history of conversion is known
- must always specify encoding used, e.g. for text, input, output



## Terminology

### Character

- minimal unit of text with semantic value
- e.g. a letter

### Character set

- a set of characters
- e.g. the English language
- also called charset

### Character encoding

- unique mapping of characters to numbers
- also only called encoding

### Coded character set

- a character set for which an encoding is specified

### Code space

- set of numbers to which a coded character set is mapped

### Code point

- element of code space
- i.e. a number



## Resources

- [David Zentgraf - What Every Programmer Absolutely, Positively Needs To Know About Encodings And Character Sets To Work With Text](http://kunststube.net/encoding/)
- [Joel Spolsky - The Absolute Minimum Every Software Developer Absolutely, Positively Must Know About Unicode and Character Sets (No Excuses!)](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)
- [Wikipedia - Character encoding](https://en.wikipedia.org/wiki/Character_encoding)
