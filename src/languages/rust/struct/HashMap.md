# HashMap



## Introduction

- collection type
- key-value pairs
- dynamic length
- different types, both key and values can be any type
- iterable
- beware: wants to iterate over reference, otherwise moves elements into loop variable and can't use map afterwards ❗️

stores in underlying Vec, keys and value in element
keys are hashed, inserted in order of hash
key type needs to implement `Hash`, but not `Ord`
hash range is constrained to capacity
if hash collision uses more levels of hashing, slightly decreased performance
random ordering because of hash, changes with each allocation
beware: don't rely on iteration order ❗️
to avoid collisions keeps saturation lower, not full, not so memory efficient



## Resources
