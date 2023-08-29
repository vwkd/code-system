# Macro



## Introduction

- expanded after AST is constructed, before semantic analysis validates AST
- can be declarative or procedural



## Declarative

- matches against pattern
- maps input patterns to match arms
- beware: different pattern syntax than in match expression ❗️
- can accept variable number of arguments
- can pass different types as arguments
- also called macro by example
- most widely used form

### Declaration

- can contain other macros
- variables and identifiers are scoped to macro
- doesn't leak into surrounding scope

### Usage

- calls with exclamation mark and grouping tokens
- e.g. parentheses, brackets, curly brackets, etc.



## Procedural

- function with token stream input and token stream output
- currently must be defined in own crate with special crate type

### function-like

- like declarative

### custom derive

- argument to `derive` attribute
- can't have arguments
- allows automatic implementations for user-defined types
- e.g. functions, traits, modules, etc.

### attribute-like

- own attribute
- can have arguments



## Println

?? takes argument by reference even if not specified? `println!("{}", foo.bar)`