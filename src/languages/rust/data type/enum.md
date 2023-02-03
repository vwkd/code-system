---
title: Enum
index: 7
---

## Introduction

- grouping of variants
- can add primitive type, tuple, or struct
- use double colon to select variant
- can implement methods and associated functions, like structs
- `Option` enum to represent exitstence or non-existence, no null value, forced to handle non-existence case
- variant is also constructor function for itself, e.g. `Foo::Bar` is like closure `|v| Foo::Bar(v)`

```rs
enum Foo {
  Bar(u8)
}

let v = [1, 2, 3];
let w = v.map(Foo::Bar);
```
