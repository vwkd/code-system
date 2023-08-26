# Box



## Introduction

- smart pointer
- stores value on the heap
- used to transfer ownership ("derivation") of large value without copying it
- used for trait object generic
- used to make sized type from unsized type
- automatically imported because included in prelude
- only single ownership of value, for shared ownership see `Rc`

??? Basic

reference to Box of Type can be coerced to reference to Type

not much extra functionality

allows immutable or mutable borrows

can convert to reference with `as_ref` method



## Resources
