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



## Resources
