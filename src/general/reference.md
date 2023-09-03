# Reference



## Introduction

- data type of location
- value is location of another value, usually memory address
- points to value
- can think of a pointing finger, a physical address, a page number in a book, a hypherlink, etc.
- can think of value of another value
- value always on stack
- beware: never on heap, don't confuse with value of Smart pointer, see Smart pointer ⚠️
- can dereference
- allows more performance, doesn't copy memory
- can have pointers to pointers
- potential problems since underlying data can change underneath
- also called pointer, sometimes means concrete implementation

- can think of access to someone else's memory, not your own memory
- can think of visiting someone else's house
- with their permission, you can visit, you can even change stuff, but you need to leave again



## Dereferencing

- follow location to get to value
- get value that points to
?? follows the memory address in pointer to get to value



## Smart pointer

- algebraic data type holding internal pointer to value
- usually value is on heap, de-/allocates internally
- can use like reference, transparent
- beware: often "looks through", refers to type of value, e.g. "this variable is on the heap", etc. ⚠️



## Fat pointer

- reference
- holds additional metadata for completeness
- double the size of simple reference



## Resources
