---
title: Enum
index: 7
---

## Introduction

- sum type
- can have members
- members can be associate values and methods
- replaces unions in other languages
- can be concrete or generic
- uses static polymorphism

?? stored on stack, all variants must be sized ??
?? size is equal to size of largest variant



## Declaration

- associated value can be unit, tuple or struct
- can implement methods and associated functions, like for structs



## Instantiation

- syntax is enum type followed by double colon and associated value (if any)
- variant is also constructor function for itself, e.g. `Category::Age` is like closure `|age| Category::Age(age)`

```rs
enum Category {
  Age(u8)
}

let age_limits = [21, 42, 84].map(Category::Age);
```

?? are associated values deeply mutable like for struct



## Access

- single dot on instance accesses members
- double colon on enum type accesses associated functions
- derivation of associated value like for variable, see Memory#Derivation
- beware: assigning of associated value that's not `Copy` moves it ❗️



## Resources
