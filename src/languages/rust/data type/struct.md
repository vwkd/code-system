---
title: Struct
index: 5
---

## Introduction

- grouping of related variables (fields) and functions (methods)
- no inheritance, no classes
- separate `impl` block for methods, multiple
- `self` as first argument for instance method, otherwise associated function of struct type itself
- uses single dot to access struct members, uses double colon to access associated functions

## Ownership

- assigning of non-primitive struct property moves it

## Instantiation

- define fields in any order
- single name shorthand for fields of same name as variable, adapted from JavaScript
- spread syntax shorthand for reusing remaining fields from existing struct, adapted from JavaScript

## Tuple Structs

- without named fields
- use as a named tuple, can distinguish from other (named) tuples
