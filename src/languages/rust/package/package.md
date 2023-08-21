# Package



## Introduction

- collection of crates
- has `Cargo.toml`
- at least one crate
- at most one library crate
- any number of binary crates
- created with `cargo new`
- `cargo new` by default creates binary crate, `--lib` creates library crate
- beware: often confusingly calls crate, e.g. publishing a crate, importing a crate as dependency, `crates.io`, etc.



## `Cargo.toml`

- description
- build steps for crates
- dependencies

### Features

- allows conditional compilation optional dependencies
- reduces compile time and file size
- opt-in, disabled by default
- can provide default



## `Cargo.lock`

- lockfile
- pins exact dependency versions
- automatically generated, don't edit manually
- commit, except if library crate



## Resources
