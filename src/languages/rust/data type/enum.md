---
title: Enum
index: 5
---

## Introduction

- grouping of variants
- can add primitive type, tuple, or struct
- can use `match` statement to branch on value, exhaustive, can use underscore as catch all, takes first matching, no fall-through
- use double colon to select variant
- can implement methods and associated functions, like structs
- `Option` enum to represent exitstence or non-existence, no null value, forced to handle non-existence case