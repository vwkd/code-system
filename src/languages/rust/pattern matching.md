---
title: Branch
index: ??
---

// todo: rename



## Introduction

- block executed depending on value of type
- uses pattern matching

matching and binding against the structure of a type


### Match Guard

- additional condition in addition to pattern
?? only in `match`
applies to each pattern of multiple


## `match`

?? refutable pattern

- branch on all values
- beware: exhaustive!
- can use underscore as catch all
- takes first matching, no fall-through
- can use or operator
- can use range operator  for numeric values and characters

maps pattern to expression
exhaustive, every value must be matched



## `if let`

ir/refutable pattern
but warning if irrefutable since wouldn't need it

- branch only on one value
- multiple with `else if let`
- beware: not exhaustive!



## `if`

- condition must be boolean
