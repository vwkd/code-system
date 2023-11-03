# BTreeMap



## Introduction

- collection type
- key-value pairs
- dynamic length
- different types, both key and values can be any type
- iterable
- beware: wants to iterate over reference, otherwise moves elements into loop variable and can't use map afterwards ❗️

more efficient binary tree
B is hardcoded to 6, higher is more efficient but also wastes more space
key type needs to implement `Ord`, but not `Hash` although usually is if is `Ord`
iterate in order since is sorted
more full, more memory efficient



## Resources

