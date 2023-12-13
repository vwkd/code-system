---
title: Pattern
index: ??
---



## Introduction

? matches value of type
?? match either one or more values of type

? describes structure/shape

can match
- literal
- destructured arrays/enums/structs/tuples
- variables
- wildcards
- placeholders

and or operators
ranges of values for numbers and characters

in destructuring can rename variables
can do nested destructuring

variable in pattern can shadow outer variable

underscore ignores value, doesn't bind, can use multiple times in pattern

can be irrefutable or refutable

underscore
`_`
ignore ??values

range
? ignore part of complex type
`..`
ignore multiple ??values
?? only in complex type
like multiple underscores for any missing parts
can only have single to make it unambiguous

at operator if wants to rename restructured variable and specify value as pattern, since both syntaxes collide

`ref` keyword to get reference ?? DIFFERENT IN NEWER COMPILER ? INFERRED IMPLICITLY ?
? alternatively use methods `as_ref()`, `as_mut()`, ??as_ref_mut
??? mutably borrows if expression itself is mutable borrow

- can use underscore as catch all
- can use or operator
- can use range operator for numeric values and characters

maps pattern to expression

can use multiple with `|`

match values against structures and to, optionally, bind variables to values inside these structures

Variables can be bound within the pattern
The binding mode (move, copy, or reference) depends on the pattern
?? Every binding in each | separated pattern must appear in all of the patterns in the arm. Every binding of the same name must have the same type, and have the same binding mode.

match ergonomics: when a reference is matched with a non-reference pattern, the bindings within that pattern bind by reference rather than by value
i.e. as if they were prefixed with `ref`
When a reference value is matched by a non-reference pattern, it will be automatically treated as a `ref` or `ref mut` binding
```rs
let x = &Some(0);

match x {
    Some(y) => { ... }, // `y` is a reference to `0`
    None => { ... },
}
```



## Irrefutable

?? always matches

## Refutable

?? might match or not



## Resources

- [RFC 2005 - match ergonomics](https://github.com/rust-lang/rfcs/blob/master/text/2005-match-ergonomics.md)
- [StackOverflow - Extracting a mutable reference from an Option](https://stackoverflow.com/questions/69615120/extracting-a-mutable-reference-from-an-option/69616386#69616386)
