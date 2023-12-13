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
- beware: don't implement if doesn't make sense, e.g. mutable reference for `HashSet`
- usually implements for im/mutable reference that calls `iter()`/`iter_mut()`
<!-- todo: why not the other way around? implement as part of trait and let convenience methods `iter()` and `iter_mut()` return `IntoIterator::into_iter(&mytype)` and `IntoIterator::into_iter(&mut mytype)`? -->
- beware: for owned type consumes it, instead use reference ❗️



## `iter()`

- convenience method for `(&value).into_iter()`
- beware: convention, not part of trait ❗️



## `iter_mut()`

- convenience method for `(&mut value).into_iter()`
- beware: convention, not part of trait ❗️



## other methods

- ad-hoc methods if no single way to get iterator
- e.g. `keys()` and `values()` for `HashMap`, etc.
- beware: not part of trait ❗️



## Resources

- [StackOverflow - What is the difference between iter and into_iter?](https://stackoverflow.com/questions/34733811/what-is-the-difference-between-iter-and-into-iter)
