---
title: Enum
index: 7
---

## Introduction

- sum type
- can have members
- members can be associate values and methods
- replaces unions in other languages

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



## Common enums

### Option

value or null
replaces returning null
forces null handling

implements `IntoIterator`, can be iterated over, has either 0 or 1 elements

unwrap method to panic at runtime, can use during development or when case never happens

? included in prelude

? question mark operator also works, extracts Some or returns None

? has map method that maps some of some otherwise just back to none

### Result

value or error
replaces throwing exception
forces error handling

unwrap method to panic at runtime, can use during development or when case never happens

? included in prelude

question mark operator, extracts result or returns Err ??



## Resources
