# American Standard Code for Information Interchange (ASCII)



## Introduction

- first character encoding standard for English language, created in 1960s
- included 128 essential characters, e.g. `A` is encoded as `65`
- used 7 bits in binary for each code point, stored in 1 byte
- soon world used additional 128 characters by making use of the 8th bit to create characters for their own languages
- lots of encodings were invented, basically for every keyboard
- some even used multiple bytes for one character
- different encodings worked more or less until the internet came along and information needed to be exchanged, then shit hit the fan
- one number in code space would correspond to all kinds of different characters depending on the encoding used, multiple bytes were read as distinct code points resulting in totally different characters, etc.
- information exchange became a mess
