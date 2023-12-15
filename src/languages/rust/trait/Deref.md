# Deref & DerefMut



## Introduction

- ability to use deref coercion
- beware: should only implement for smart pointer ❗️
- beware: lifetime of reference is bound by lifetime of smart pointer, e.g. can't dereference smart pointer and drop it but continue to use reference ❗️



## Deref

- for immutable reference
- `deref` method gives reference to underlying value
- dereference operator calls `deref` method
- beware: `deref` bad name, dereference operator does actual dereferencing ❗️



## DerefMut

- for mutable reference
- `deref_mut` method gives reference to underlying value
- dereference operator calls `deref_mut` method
- beware: `deref_mut` bad name, dereference operator does actual dereferencing ❗️



## Resources
