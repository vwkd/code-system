# Borrow & BorrowMut



## Introduction

- ability to convert reference to reference of target type `T`
- like `AsRef`, but
- target type must have same behavior
<!-- todo: ?? equivalent implementations for `Hash`, `Eq` and `Ord` traits, other traits too -->
- beware: not encoded in type system, only intent ❗️
- beware: not implemented when behavior differs, e.g. for `String` to `[u8]`, `String` to `Path`, etc. ❗️
- trivial blanket implementations for `T`, `&T` and `&mut T`
- allows to use type independently of ownership form, can use reference or owned value, abstracts over ownership form of type



## BorrowMut

- ability to convert mutable reference to mutable reference of target type `T`



## Resources

- [Aaron Turon - `Borrow` and `AsRef` are redundant](https://github.com/rust-lang/rust/issues/24140#issuecomment-90626264)
