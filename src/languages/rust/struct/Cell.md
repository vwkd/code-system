# Cell



## Introduction

- smart pointer
- allows interior mutability
- can mutate value using `set()` method
- can get copy of value using `get()` method if value implements `Copy`
- can't get reference to contained value, prevents mutating value with `set()` while has reference to it
- never has multiple references to contained value
- doesn't check borrowing rules dynamically at runtime
- beware: prefer over `RefCell` where possible ❗️
- beware: could reset value if sets to old variable that got before set newer value ❗️
- only single ownership over value, like `Box`
- only for single-threaded, not `Sync`
- no equivalent for multi-threaded, instead see `RwLock` and `Mutex`
- internally uses unsafe code to bypass limitations



## Resources
