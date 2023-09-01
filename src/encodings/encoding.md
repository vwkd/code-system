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

### Code point

- a number
- stored as bytes
- often implicitly assumes encoding that maps to a character

### Code space

- a set of code points
- can think of code point set
- often implicitly assumes encoding that maps to a character set

### Character encoding

- unique mapping between character set and code space
- also called encoding

### Coded character set

- a character set with an encoding



## Resources

- [David Zentgraf - What Every Programmer Absolutely, Positively Needs To Know About Encodings And Character Sets To Work With Text](http://kunststube.net/encoding/)
- [Joel Spolsky - The Absolute Minimum Every Software Developer Absolutely, Positively Must Know About Unicode and Character Sets (No Excuses!)](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/)
- [Wikipedia - Character encoding](https://en.wikipedia.org/wiki/Character_encoding)
- [Ned Batchelder - Pragmatic Unicode, or, How do I stop the pain?](https://youtube.com/watch?v=sgHbC6udIqc)
