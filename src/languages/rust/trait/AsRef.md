# AsRef & AsMut



## Introduction

- ability to convert reference to reference of target type `T`
- allows to implement for multiple target types
- implementations for most smart pointers, e.g. `String` to `str` or `[u8]` or `Path`, `Vec<T>` to `[T]`, `Box<T>` to `T`, `Rc<T>` to `T`, `Arc<T>` to `T`, `Cow<T>` to `T`, etc.
- allows to give reference to underlying data
- e.g. borrow single field of struct, etc.
- should be cheap, for expensive see `From`
- beware: not encoded in type system, only intent ❗️
- beware: only explicit, for implicit conversion see `Deref` ❗️
- trivial blanket implementations for `&S` and `&mut S` if implements for `S`
- allows to use type independently of ownership form, can use reference or owned value, abstracts over ownership form of type
- beware: not necessary for call `ref_s.as_ref()` since dot operator automatically dereferences to `(*ref_s).as_ref()`, but still necessary in argument since otherwise wouldn't accept reference ❗️

<!-- todo: why has no blanket implementation for types that implement `Deref` to target type that implements `AsRef` -->



## AsMut

- ability to convert mutable reference to mutable reference of target type `T`



## Resources
