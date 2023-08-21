# Test



## Introduction

- function with `#[test]` attribute
- by convention in `tests` module with `#[cfg(test)]` configuration attribute
- can use `assert` macros
- can return `Result` enum
- can run with `cargo test`



## Unit test

- by convention along source code in child module
- beware: not in top-level `test` directory ❗️



## Integration test

- in top-level `test` directory
- each file gets compiled as a separate crate
- files in subdirectories aren't treated as tests
- can use child module in subdirectory to share code



## Resources

- [Let's Get Rusty Bootcamp - Unit Tests](https://portal.letsgetrusty.com/bootcamp/post/58)
- [Let's Get Rusty Bootcamp - Integration Tests](https://portal.letsgetrusty.com/bootcamp/post/59)
