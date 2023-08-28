# Deref & DerefMut



## Introduction

- ability to dereference reference to type
- allows to use deref coercion
- allows to use smart pointers like reference
- beware: should only use for smart pointer ❗️



## Deref

- for immutable reference
- `deref` method gives reference to underlying value
- dereference operator calls `deref` method
- beware: `deref` bad name, because only gives other reference, dereference operator does actual dereferencing ❗️



## DerefMut

- for mutable reference
- `deref_mut` method gives reference to underlying value
- dereference operator calls `deref_mut` method
- beware: `deref_mut` bad name, dereference operator does actual dereferencing ❗️



## Resources
