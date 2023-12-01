# Macro



## Introduction

- expanded after AST is constructed, before semantic analysis validates AST
- can be declarative or procedural



## Declarative

- maps input patterns to expression
- can think of substitution
- matches pattern against single token tree
- beware: different pattern syntax than in match expression ❗️
- can accept variable number of arguments
- can pass different types as arguments
- also called macro by example
- most widely used form
- input must be valid syntax
- beware: unlike procedural, which can define arbitrary syntax ❗️

### Declaration

- using `macro_rules!` macro
- match arms like `match` statements
- use block to contain statements
- has separate scope for identifiers
- doesn't leak identifiers into caller's scope
- needs to pass identifiers of caller's scope as argument to access it
- beware: don't confuse with function call, doesn't pass value but access to identifier ❗️
- can contain other macros
- annotate with `#[macro_export]` to make public

### Usage

- calls with exclamation mark and grouping tokens
- e.g. parentheses, brackets, curly brackets, etc.
- beware: can't restrict to specific grouping tokens, e.g. only square brackets ❗️



## Procedural

- maps input token stream to output token stream
- can think of program
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



## Resources

- [Jon Gjengset - Crust of Rust: Declarative Macros](https://youtube.com/watch?v=q6paRBbLgNw)
