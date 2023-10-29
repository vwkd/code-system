# RefCell



## Introduction

- smart pointer
- allows interior mutability
- like `Cell`, but doesn't require contained type to be copyable
- can get immutable reference using `borrow` method
- can get mutable reference using `borrow_mut` method
- checks borrowing rules dynamically at runtime
- panics at runtime if violates borrowing rules
- internally uses unsafe code to bypass limitations
- performance penalty due to extra check at runtime



## Resources
