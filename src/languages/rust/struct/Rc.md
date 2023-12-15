# Rc



## Introduction

- smart pointer
- counts references
- allows shared ownership
- beware: multiple owners is misleading, itself is single owner, others only have references ❗️
- increments reference count for each new reference
- cleans up when reference count reaches zero
- like light with sensor, first person who enters turns it on, after last person leaves turns itself off
- stores two counts, strong count and weak count
- strong count is number of references that have ownership of value
- weak count is number of references that don't have ownership of value
? beware: can still have non-zero weak count after value is dropped
- stores value on heap, since not clear whose stack exists the longest
- only immutable borrows, mutable would violate borrowing rules
- for shared mutable ownership wrap value in `RefCell`
- only for single-threaded, not thread-safe, not `Send` and `Sync`
- for multi-threaded see `Arc`



## Storage

Arc
has cheap constant time clone
doesn't need capacity field since can't mutate
also implements `Deref<[T]>` like `Vec<T>`
-> can replace Vec<T> if doesn't need mutation

`Arc<str>` can make cheaper clones, just copies struct on stack, increments reference count

///

Arc<str>
heap data is strong rc, weak rc, and string data

arc struct is pointer to heap data and length, no capacity
if type is Sized then only pointer, no length

clone just increments rc and copies struct, doesn't clone heap data / memory allocation / deep copy

also implements `Deref<str>` like `String`
-> can replace String if doesn't need mutation

Shared-ownership immutable string
unlikely benefits, only when
 do tons and tons of copy of long permanent text, and
 can't attach a string ownership with anything else in the same scope at all

--> in short: use Arc for shared ownership instead of cloning Vec, but if references won't do

ABOVE BAD
get a pointer to the same exact slice
like taking an immutable reference to a Vec, which is faster
 does not fulfil the same role as a Vec clone

## Usage

- get reference using `clone` method or associated function
- beware: doesn't clone value ⚠️
- beware: by convention use associated function to distinguish it from `clone` method in other types ⚠️
- clone is cheap, constant time



## Resources
