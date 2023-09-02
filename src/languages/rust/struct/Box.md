# Box



## Introduction

- smart pointer
- stores value on heap
- used to transfer ownership ("derivation") of large value without copying it
- used for trait object generic
- used to make sized type from unsized type
- only single ownership of value, for shared ownership see `Rc`
- automatically imported because included in prelude

can convert to reference with `as_ref` method

- implements closure traits
- can use boxed closure trait object where expects generic with closure trait bound

always use &T instead of &Box<T>


## Storage

stores heap data
is struct with pointer to heap data and length
if type is Sized then only pointer, no length
even more efficient than Arc
but clone would deep copy
can think of immutable Vec<T> without capacity



or even better Box<str> if doesn't need to clone
Box<str> is essentially immutable String, no allocation, also no capacity
cloning Box<str> would make deep clone, memory allocation, linear time copy
BUT always prefer to use references to slice first, if doesn't need ownership



## Resources
