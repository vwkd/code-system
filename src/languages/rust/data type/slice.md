# Slice



## Introduction

- composite collection type
- variable-length sequence of values of single type
- can think of unsized array
- dynamically sized
- beware: often uses "slice" as synonym for "reference to slice" ⚠️
- clone is expensive, linear time



## Reference

- fat pointer, also holds length
- can create from statically sized collection
- beware: collection value can be anywhere, e.g. stack, heap, static memory ❗️
- syntax is leading ampersand and trailing brackets containing range
- can think of view or window into collection
- tied to existing collection



## Resources

- [Stack Overflow - What is the difference between a slice and reference in Rust?](https://stackoverflow.com/a/61151916/2607891)
