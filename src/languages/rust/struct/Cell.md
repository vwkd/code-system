# Cell



## Introduction

- interior mutability

moves values in and out of the cell
an &mut T to the inner value can never be obtained
the value itself cannot be directly obtained without replacing it with something else
i.e. never more than one reference pointing to the inner value


typically used for more simple types where copying or moving values isn’t too resource intensive (e.g. numbers)
should usually be preferred over other cell types when possible
For larger and non-copy types, RefCell provides some advantages.

- beware: allows to mutate through immutable reference ❗️



## Resources
