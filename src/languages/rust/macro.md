# Macro



## Introduction

- expanded after AST is constructed, before semantic analysis validates AST
- can be declarative or procedural



## Declarative

- maps input patterns to expression
- can think of substitution
- matches pattern against single token tree
- beware: different pattern syntax than in match expression ❗️
- can accept variable number of patterns
- can pass different types as patterns
- also called macro by example
- most simple, less powerful
- input must be valid syntax
- beware: unlike procedural, which can define arbitrary syntax ❗️

### Declaration

- using `macro_rules!` macro
- match arms like `match` statements
- use block to contain statements
- hygienic, has isolated scope
- doesn't leak identifiers into caller's scope
- needs to pass identifiers of caller's scope as pattern to access it
- beware: don't confuse with function call, doesn't pass value but access to identifier ❗️
- can contain other macros
- annotate with `#[macro_export]` to make public
- use repetition in patterns and body
- can specify separator, defaults to whitespace
- can specify repetition zero or one, zero or more, one or more
- beware: can't specify exact number of repetitions ❗️
- can use repetition for a pattern in body
- can use multiple repeating patterns only if repeat same number of times
- beware: can't use multiple patterns that repeat different amount of times because ambiguous ❗️
- beware: use expression input only once, otherwise if first evaluation mutates underlying data then second evaluation fails to compile, instead can assign to local variable once and reuse that multiple times ❗️
- compile error in body is propagated to input, i,e, can't specify input type like in function, just uses it and let error

### Usage

- calls with exclamation mark and grouping tokens
- e.g. parentheses, brackets, curly brackets, etc.
- beware: can't restrict to specific grouping tokens, e.g. only square brackets ❗️



## Procedural

- maps input token stream to output token stream
- can think of program
- more complex, most powerful
- can emit better error messages
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
