---
title: String
index: 2
---

## Introduction

- two types of strings
- more complicated, but more correct

## `String`

- heap-allocated growable owned
- UTF-8 encoding
- like `Vec<u8>` but always valid UTF-8

## `&str`

- string slice for some string in memory
- string not necessarily heap, can be in binary as well
- can only use reference directly since size is not known at compile-time for stack
- `&String` gets automatically coerced to `&str`

## String literal

- stored in binary directly
- string slice pointing to address in binary
