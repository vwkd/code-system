---
title: Enum
index: 7
---

## Introduction

- grouping of variants

Sum Type / Variant Type, type is any one of its variants

replaces unions in other type systems

variant can be unit (no value), struct, tuple

- can add primitive type, tuple, or struct
- use double colon to select variant
- can implement methods and associated functions, like structs

- variant is also constructor function for itself, e.g. `Foo::Bar` is like closure `|v| Foo::Bar(v)`

```rs
enum Foo {
  Bar(u8)
}

let v = [1, 2, 3];
let w = v.map(Foo::Bar);
```

?? stored on stack, all variants must be sized ??
?? size is equal to size of largest variant


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