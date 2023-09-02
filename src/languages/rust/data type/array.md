# Array



## Introduction

- composite collection type
- fixed-length sequence of values of single type
- statically sized
- for different types can wrap in enum with attached values



## Usage

- iterable
- beware: usually wants to iterate over reference, otherwise moves elements into loop variable and can't use array afterwards ❗️
- index can be range
- index can be dynamic
- beware: direct index copies element, instead can get reference using `get` method ❗️
- beware: must use reference for heap-allocated data type since move is not possible ❗️
- beware: can't access and also mutate elements, would be two borrows where at least one is mutable, e.g. `arr[0]; arr[1] = 1;` ❗️
- `&[T; N]` coerces into `&[T]`
- best practice to use `&[T]` instead of `&[T; N]`
- beware: doesn't implement `Deref`, instead compiler magic ❗️



## Resources
