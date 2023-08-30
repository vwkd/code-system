# String



## Introduction

- smart pointer
- owned string

- heap-allocated growable owned
- UTF-8 encoding
- like `Vec<u8>` but always valid UTF-8
? similar to `Vec<char>`

?? is already a pointer to data on the heap
?? every heap-allocated data type is a pointer to a value on the heap
reference is a pointer to a pointer
avoid extra layers of indirection, e.g. pointer to pointer to pointer...
function argument type should be coercion target, e.g. `&str` instead of `&String`, slice instead of array or vector

implements deref trait to str

- in standard library
- automatically imported because included in prelude



## Resources
