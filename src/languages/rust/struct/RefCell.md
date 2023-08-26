# RefCell



## Introduction

- smart pointer
- provides reference checked at runtime
- allows interior mutability
- checks borrowing rules dynamically at runtime
- no borrow rules check statically at compile time
- panics at runtime if violates borrowing rules
- performance penalty due to extra borrowing rules check
- internally uses unsafe code to bypass limitations
- only single ownership over value, like Box
- only single-threaded, not `Sync`
- for multiple threads see `RwLock`



## Usage

- get immutable reference using `borrow` method
- get mutable reference using `borrow_mut` method



## Resources
