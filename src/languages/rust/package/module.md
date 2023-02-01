---
title: Module
index: 6
---

## Introduction

- using `mod` keyword, has module tree
- members of child modules are private by default, need to opt-in to make public, needs to make public to use
- members of parent modules are public, child module can use everything, needs to use `super`?
- for struct needs to make also fields public, can't create struct directly (without associated function) if any field isn't public
- can use by specifying relative or absolute path of module tree, double colons for separation
- can bring path into scope using `use` keyword, can also rename, reexport, group multiple nested, or any using glob
- files also create modules, module name is filename without `.rs` extension, tree is nested folders, can bring into scope using `mod` keyword, still needs to use `use` keyword if wants shorter path