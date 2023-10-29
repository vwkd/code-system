# RwLock



## Introduction

- smart pointer
- allows interior mutability
- like `RefCell`, but works for multiple threads
- can get immutable reference using `read()` method
- can get mutable reference using `write()` method
- allows multiple readers or single writer
- blocks until can aquire lock
- beware: potential for deadlocks ❗️

