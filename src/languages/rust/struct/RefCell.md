# RefCell



## Introduction

- smart pointer
- allows interior mutability
- checks borrowing rules dynamically at runtime
- panics at runtime if violates borrowing rules
- doesn't check borrowing rules statically at compile time
- performance penalty due to extra check at runtime
- internally uses unsafe code to bypass limitations
- only single ownership over value, like `Box`
- only single-threaded, not `Sync`
- for multiple threads see `RwLock`



## Usage

- get immutable reference using `borrow` method
- get mutable reference using `borrow_mut` method



## Resources
