# RefCell



## Introduction

smart pointer

?? Can get temporary ownership to mutate Rc

enables interior mutability
decreased performance due to checking borrowing rules at runtime instead of compile time

don't do `Rc::new(RefCell::new(..))`
similarly counterparts Arc and Mutex

// todo: understand last part of https://m.youtube.com/watch?v=PbR4ECFIckg

single ownership over value, like Box
but unlike Box enforces borrowing rules dynamically at runtime instead of at compile time
performance penalty, overhead of checking borrowing rules

internally uses unsafe code to bypass limitations, no borrow rules check at compile time
implements own expanded borrowing rules checks at runtime

Only in single threaded program

allows immutable or mutable borrows checked at runtime

beware: can have mutable value inside RefCell even though RefCell itself is declared immutable
"interior mutability pattern"

with references and Box etc. can't mutable borrow if underlying value is immutable
also can't mutate mutabler value through immutable borrow

can solve with indirection, data structure (struct) holds mutable value, can mutate it internally through methods
gets immutable reference to data structure
"interior mutability pattern"

RefCell is fancy such data structure
but instead of mutation through methods
calls methods to get an im/mutable reference to value
RefCell checks at runtime that references are values

? can combine with Rc to get multiple owners of mutable value



## Resources
