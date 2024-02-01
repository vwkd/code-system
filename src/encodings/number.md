# Number representation



## Introduction

method to represent number
sequences of bits

how to assign numbers to bits
could be any random map
choses maps with good properties
  simple circuitry
  simple addition, subtraction, comparison



## Integer

### Unsigned

simply count in base 2 / binary

range is 0 to 2^N-1 for N bits

### Signed

#### Sign–magnitude

- simplest
- also called signed magnitude

negative value
toggle highest-order bit

- complex circuits
can represent negative zero

sign bit
sign of number
often the most significant bit
0 for a positive number
1 for a negative number

remaining bits
magnitude of number

can think of gluing non-negative part and reversed non-positive part of number line together

##### Advantages

##### Disadvantages

- has negative zero, two zeros
- ?? addition and subtraction requires different circuits
- ?? comparison also requires inspecting the sign bit
- minimum negative number is 2^(bits-1)-1, e.g. for 1 byte (8 bits) it's −127

#### Ones' complement

negative value
invert all of the bits in its positive value
bitwise NOT ("complement") of positive number

can think of gluing non-negative part and non-positive part of number line together

- simpler circuits

##### Advantages

- ?? addition and subtraction conventional binary addition and just do an end-around carry, can ignore the sign bit

##### Disadvantages

- has negative zero, two zeros

#### Two's complement

like ones' complement, but plus one
bitwise NOT ("complement") of positive number plus one

most significant bit represents inverse of value in an unsigned integer
can think of counting up from minimum

can think of gluing non-negative part and negative part of number line together
arithmetic drops last bit if overflows
modular arithmetic (mod 2^N)
?? unsigned numbers wrap around
can think of gluing ends of number line together

- simplest circuits
- most common

allows us to share the signed and unsigned arithmetic logic

##### Advantages

- ?? addition and subtraction conventional binary addition and depend on the overflow behavior, can ignore the sign bit
- ?? comparison can simply subtract the two numbers, and check if the outcome is positive or negative
- no negative zero, single zero
- minimum negative number is 2^(bits-1), e.g. for 1 byte (8 bits) it's −128

##### Disadvantages

#### Offset binary

signed number representation
bit pattern corresponding to unsigned number
plus biasing value or offset (K)

0 is represented by K
−K is represented by 0

?? two's complement is offset `2^(N−1)`

offset unsinged down by 2^(N-1)
range from −2^(N-1) to 2^(N-1)-1

- also called excess-K or biased

for offset 128
can think of normal number line

##### Advantages

- no negative zero, single zero

##### Disadvantages

?? non-negative bit patterns don't match with unsigned
needs separate addition, subtraction, comparison...

### Example

e.g. 1 byte

| Binary   | Unsigned | Sign–magnitude | Ones' complement | Two's complement | Offset 128 |
|----------|----------|----------------|------------------|------------------|------------|
| 00000000 | 0        | 0              | 0                | 0                | −128       |
| 00000001 | 1        | 1              | 1                | 1                | −127       |
| ⋮        | ⋮        | ⋮              | ⋮                | ⋮                | ⋮          |
| 01111101 | 125      | 125            | 125              | 125              | -3         |
| 01111110 | 126      | 126            | 126              | 126              | -2         |
| 01111111 | 127      | 127            | 127              | 127              | −1         |
| 10000000 | 128      | −0             | −127             | −128             | 0          |
| 10000001 | 129      | −1             | −126             | −127             | 1          |
| 10000010 | 130      | −2             | −125             | −126             | 2          |
| ⋮        | ⋮        | ⋮              | ⋮                | ⋮                | ⋮          |
| 11111101 | 253      | −125           | −2               | −3               | 125        |
| 11111110 | 254      | −126           | −1               | −2               | 126        |
| 11111111 | 255      | −127           | −0               | −1               | 127        |



## Float



## Resources

https://en.wikipedia.org/wiki/Signed_number_representations
- [Mabi - How Computers Use Numbers](https://mabi.land/numbers/)
https://ciechanow.ski/exposing-floating-point/
