# RwLock



## Introduction

- smart pointer
- allows interior mutability
- allows multiple readers or single writer
- like `RefCell`, but
- for multi-threaded, thread-safe, `Send` and `Sync`
- uses atomic counters
- can get immutable reference using `read` method
- can get mutable reference using `write` method
- blocks until can aquire lock instead of panicking,
synchronized
- beware: potential for deadlocks ❗️
