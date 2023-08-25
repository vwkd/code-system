# Rc



## Introduction

smart pointer

Reference counted smart pointer
Not send and sync

multiple owners
- allows shared ownership of value
- keeps reference count, when zero cleans up

call `.clone()` on smart pointer to produce second one

?? can't mutate

like shared TV, first person who enters turns it on, last person who leaves turns it off
?? but no one person responsible, instead turns itself off

?? only in single threaded programs

get another reference with `clone` method or associated function
doesn't clone value, just reference??
increments reference count

allows only immutable borrows
only allows reading, not mutation, would violate borrowing rules
-> see RefCell

stores two counts
strong count is number of references that have ownership of value
weak count is number of references that don't have ownership of value
? beware: can still have non-zero weak count after value is dropped



## Resources
