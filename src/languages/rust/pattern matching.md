---
title: Branch
index: ??
---

// todo: rename



## Introduction

- conditionally executed block
- uses pattern
- expression, can return value

matching and binding against the structure of a type

note: doesn't need to be enum, can match values of any type like struct



## `match`

- branch on all values
- beware: exhaustive, every value must be matched ❗️
- ?? takes refutable pattern
- takes first matching branch, no fall-through
- can think of definitely branch

### Match Guard

- additional boolean condition
- syntax trailing `if`
- applies to each pattern if multiple
- short-circuited, only evaluated if pattern matches
- beware: evaluated multiple times if multiple patterns match but condition is `false` ❗️



## `if let`

- branch only on some values
- beware: not exhaustive ❗️
- takes refutable pattern
- beware: also takes irrefutable pattern, but warning since doesn't need it, since always matches ❗️
- can add more branches with `else if let`
- can think of maybe branch

can do AND by matching tuple of both



## `if`

- condition must be boolean
