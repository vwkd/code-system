# Rc



## Introduction

- smart pointer
- counts references
- allows shared ownership of value
- beware: multiple owners is misleading, itself is single owner, others only have references ❗️
- increments reference count for each new reference
- cleans up when reference count reaches zero
- like light with sensor, first person who enters turns it on, after last person leaves turns itself off
- stores two counts, strong count and weak count
- strong count is number of references that have ownership of value
- weak count is number of references that don't have ownership of value
? beware: can still have non-zero weak count after value is dropped
- stores value on heap
- not `Send` and `Sync`
- only for single-threaded, not thread-safe
- for multi-threaded see `Arc`
- only immutable borrows, mutable would violate borrowing rules
- for shared mutability wrap value in `RefCell`



## Usage

- get reference using `clone` method or associated function
- beware: doesn't clone value ⚠️
- beware: by convention use associated function to distinguish it from `clone` method in other types ⚠️



## Resources
