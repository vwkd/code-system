# RefCell



## Introduction

- smart pointer
- allows interior mutability
- like `Cell`, but
- can get immutable reference using `borrow` method
- doesn't require contained type to be copyable
- can get mutable reference using `borrow_mut` method
- checks borrowing rules dynamically at runtime
- panics at runtime if violates borrowing rules
- performance penalty due to extra check at runtime
- only for single-threaded, not thread-safe, not `Sync`
- for multi-threaded see `RwLock`



## Resources
