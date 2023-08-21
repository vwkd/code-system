---
title: Module
index: 9
---

## Introduction

- organizes code for readability and reuse
- controls scope and visibility
- has module tree
- tree is nested folders



## Declaration

- using `mod` keyword and block
- can have multiple modules per file
- beware: could have all modules in single file, doesn't need files like in other languages ❗️
- can use files
- child modules are sibling files with filename without `.rs` extension as module name
- grandchild modules are in subfolder with module name of child module as folder name
- can also put child module into its folder as `mod.rs`
- beware: file contains not necessarily only one module like in other languages ❗️



## Usage

- bring child module into scope with `mod` keyword and module name
- beware: must always manually declare child module, even if in same file ❗️
- beware: doesn't need `mod` for external dependencies ❗️
- can access using relative or absolute path in module tree
- double colons for separation
- `super` for parent module
- can additionally bring subpath into scope with `use` keyword
- can rename
- can group multiple nested
- can use wildcard
- beware: `use` still requires `mod` first ❗️
?? can also bring public member into scope if descendant module itself isn't public



## Visibility

- members of descendant modules are private by default
- opt-in to make public to ancestor modules with `pub` keyword
- members of ancestor modules are public by default
- descendant modules can access everything from ancestor modules
- can reexport with `pub use` keyword
- beware: can't instantiate public struct if has any private field, instead use constructor function like associated function `new` ❗️



## Resources
