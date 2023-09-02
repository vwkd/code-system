# Slice



## Introduction

- collection type
- variable-length sequence of values of single type
- can think of unsized array
- dynamically sized
- value can be anywhere, e.g. stack, heap, static memory
- reference is fat pointer, also holds length
- beware: often uses "slice" as synonym for "reference to slice" ⚠️



## Create

- can create immutable reference to slice from statically sized collection
- syntax is leading ampersand and trailing brackets containing range
- can think of view or window into collection
- tied to existing collection



## Resources

- [Stack Overflow - What is the difference between a slice and reference in Rust?](https://stackoverflow.com/a/61151916/2607891)
