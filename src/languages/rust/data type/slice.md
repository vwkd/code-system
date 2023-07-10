# Slice



## Introduction

pointer to data and length of data

dynamically-sized view into a contiguous sequence of elements in memory

- reference to fixed-size part of a collection, e.g. array, vec, etc.
- can think of as view or window into data
- points to data directly, but still tied to existing variable?!?

- dynamically sized, because size unknown at compile time

- reference to slice is fat pointer, contains address and size
- ??? beware: often uses reference of slice since to get statically sized!

- beware: often uses "slice" as synonym for "reference to slice"!



???

reference to owned type can be automatically coerced to slice
e.g. &String to &str
