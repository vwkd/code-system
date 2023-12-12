# IntoIterator



## Introduction

- ability to create iterator for type
- calls type that implements it "iterable"
- allows to use type in for loop



## Implementation

- method `into_iter()` returns wrapper iterator type, e.g. `IntoIter`, `Iter`, `IterMut`
- associated type `IntoIter` is wrapper iterator type and `Item` is its item type
- automatically implemented for `Iterator`, just returns itself
- can implement for owned type, reference and mutable reference
- usually implements for im/mutable reference that calls `iter()`/`iter_mut()`
<!-- todo: why not the other way around? uses this implementation and let convenience methods `iter()` and `iter_mut()` return `IntoIterator::into_iter(&mytype)` and `IntoIterator::into_iter(&mut mytype)`? -->
- beware: for owned type consumes it, instead use reference ❗️



## `iter()`

- method of type that returns iterator over immutable reference to values
- beware: convention, not part of trait ❗️



## `iter_mut()`

- method of type that returns iterator over mutable reference to values
- beware: convention, not part of trait ❗️
- doesn't implement if mutation doesn't make sense, e.g. `HashSet`



## Resources
