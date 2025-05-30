# Slice



## Introduction

- composite collection type
- variable-length sequence of values of single type
- can think of unsized array
- dynamically sized
- part of existing collection value in memory, doesn't exist by itself
- can't create, only coerce from existing collection, must be statically sized
- beware: existing collection value can be anywhere, e.g. stack, heap, static memory ❗️
- can think of view into existing collection
- beware: often uses "slice" as synonym for "reference to slice" ⚠️
- clone is expensive, linear time
- `[T]`
- syntax is trailing brackets containing range or `as_ref()` method
- beware: use array indexing to prevent temporary value from being dropped early ❗️

- contiguous sequence of values in memory

- beware: can only change values, not add or remove values, e.g. for string slice can ASCII lowercase but not Unicode lowercase since might change number of characters ❗️



## Reference

- fat pointer, also holds length



## Resources

- [Stack Overflow - What is the difference between a slice and reference in Rust?](https://stackoverflow.com/a/61151916/2607891)
