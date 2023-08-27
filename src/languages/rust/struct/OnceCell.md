# OnceCell



## Introduction

- interior mutability

hybrid of Cell and RefCell
 works for values that typically only need to be set once
reference can be obtained
  without moving or copying the inner value unlike Cell
  but also without runtime checks unlike RefCell)
However, its value can also not be updated once set
unless you have a mutable reference

- only single-threaded, not `Sync`
- for multiple threads see `OnceLock`

- beware: allows to mutate through immutable reference ❗️



## Resources
