# Cell



## Introduction

- smart pointer
- allows interior mutability
- can mutate value using `set()` method
- can get copy of value using `get()` method if value implements `Copy`
- can't get reference to contained value
- never has multiple references to contained value
- doesn't check borrowing rules dynamically at runtime
- beware: prefer over `RefCell` where possible ❗️
- only single ownership over value, like `Box`
- only single-threaded, not `Sync`
- beware: doesn't implement `Sync`, loses ability to share across threads ❗️ 
- for multiple threads see `RwLock` and `Mutex`



## Resources
