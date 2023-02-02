---
title: Pattern Matching
index: 8
---

## Introduction

- branch on value of type
- can use `_` to ignore values, e.g. in complex type
- can use `..` to ignore multiple values, e.g. in complex type
- beware: can only have single `..` to make it unambiguous!



## `match`

- branch on all values
- beware: exhaustive!
- can use underscore as catch all
- takes first matching, no fall-through
- can use or operator
- can use range operator  for numeric values and characters

### Match Guard

- additional condition in addition to˝ pattern



## `if let`

- branch only on one value
- multiple with `else if let`
- beware: not exhaustive!



## `while let`

- loop as long as one value
