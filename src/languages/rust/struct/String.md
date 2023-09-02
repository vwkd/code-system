# String



## Introduction

- smart pointer
- owned string
- beware: `Vec<char>` is usually larger than equivalent `String` of same characters, since UTF-32 instead of UTF-8 ❗️

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

String is to str, what Vec<T> is to [T]
always use &str instead of &String

string data is character buffer on heap
over-allocates a bit

string struct stores pointer to string data, length and capacity

clone allocates new memory, copies over characters
linear time
no extra capacity
crates new struct and points at new character buffer

Arc<str>
heap data is strong rc, weak rc, and string data

arc struct is pointer to heap data and length, no capacity
if type is Sized then only pointer, no length

clone just increments rc and copies struct, doesn't clone heap data / memory allocation / deep copy

also implements `Deref<str>` like `String`
-> can replace String if doesn't need mutation

String for modifying collection
don't use if doesn't modify
in other words: immutable String doesn't make sense !

Shared-ownership immutable string
unlikely benefits, only when
 do tons and tons of copy of long permanent text, and
 can't attach a string ownership with anything else in the same scope at all

[a]rc a clone is always O(1), while for a slice it's O(n)

--> in short: use Arc for shared ownership instead of cloning Vec, but if references won't do

ABOVE BAD
get a pointer to the same exact slice
like taking an immutable reference to a Vec, which is faster
 does not fulfil the same role as a Vec clone



## Resources
