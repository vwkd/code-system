# Crate



## Introduction

- module tree
- can be library or binary
- has crate root



## Library

- code that other crates can use
- crate root is `src/lib.rs`



## Binary

- executable program
- crate root is `src/main.rs`

crate root of additional binary crates is `src/bin/<crate name>.rs`



## Crate root

- root module of crate
- needs `main` function if binary
- beware: in code called "crate", very confusing ❗️
- calls code from other crates "foreign"



## Resources
