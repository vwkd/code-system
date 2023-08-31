# String



## Introduction

- smart pointer
- owned string

- heap-allocated growable owned

- can think of `Vec<u8>` without illegal numbers

?? is already a pointer to data on the heap
?? every heap-allocated data type is a pointer to a value on the heap
reference is a pointer to a pointer
avoid extra layers of indirection, e.g. pointer to pointer to pointer...
function argument type should be coercion target, e.g. `&str` instead of `&String`, slice instead of array or vector

implements deref trait to str

- `&String` gets automatically coerced to `&str`
reference to string can get coerced to string slice

- in standard library
- automatically imported because included in prelude

ptr: reference to value on heap
len: length
cap: capacity

`clone()` copies heap-data, then new struct on stack
but doesn't over-allocate, capacity is same as length
linear time
`Arc<str>` can make cheaper clones, just copies struct on stack, increments reference count
or even better Box<str> if doesn't need to clone
Box<str> is essentially immutable String, no allocation, also no capacity
cloning Box<str> would make deep clone, memory allocation, linear time copy
BUT always prefer to use references to slice first, if doesn't need ownership



## Resources
