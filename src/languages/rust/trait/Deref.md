# Deref & DerefMut



## Introduction

- ability to use deref coercion
- beware: should only implement for smart pointer ❗️
- beware: lifetime of reference is bound by lifetime of smart pointer, e.g. can't dereference smart pointer and drop it but continue to use reference ❗️
- beware: only for single target type, no generic parameter ❗️



## Deref

- for immutable reference
- `deref` method gives reference to underlying value
- dereference operator calls `deref` method
- beware: `deref` bad name, dereference operator does actual dereferencing ❗️
- trivial blanket implementations for `&T` and `&mut T`



## DerefMut

- for mutable reference
- `deref_mut` method gives reference to underlying value
- dereference operator calls `deref_mut` method
- beware: `deref_mut` bad name, dereference operator does actual dereferencing ❗️
- trivial blanket implementations for `&mut T`



## Resources
