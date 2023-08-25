# Box



## Introduction

smart pointer

??? Basic

reference to Box of Type can be coerced to reference to Type

allows to allocate value on the heap

not much extra functionality

can use when needs sized type but doesn't know size
can use when wants to transfer ownership of large value without copying it
can use wir trait object, dynamic?? polymorphism, specifies trait instead of concrete type

use e.g. for recursive enum

allows immutable or mutable borrows

can convert to reference with `as_ref` method



## Resources
