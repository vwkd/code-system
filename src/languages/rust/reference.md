# Reference



## Introduction

- safe pointer
- doesn't own value, is owned by other variable
- also called "borrow"
- beware: data can be on stack or heap, e.g. integer, array, struct
- points to variable (on stack), follows that variable to get to data
- lifetime must be smaller than variable it references, prevents dangling pointer
- when it goes out of scope nothing happens, data is not dropped
- scope is between declaration and last use, smaller than variable scope
- can have either multiple immutable references or single mutable reference in a scope, e.g. prevents data races
- can't use existing variable in meantime??

mutable reference coerces to immutable reference

note, reference and value aren't equal, different types, e.g. `5 == &5`

can still create memory leaks with reference cycles, e.g. using Rc and RefCell
can maybe replace one Rc with Weak

weak pointer: doesn't own value
strong pointer??: owns value


## Lifetime annotation

???
minimum lifetime
can assign any same type with longer lifetime
- minimum lifetime of input reference, maximum lifetime of output reference
- specified as another reference lifetime
- ??usually output reference lifetime 
- specifies minimum lifetime of output reference is at least lifetime of input reference, not exact same lifetime
- beware: doesn't change lifetime, just clarifies relationships!
- necessary when can't infer ("elide")
  - references in function return type with multiple references in function arguments
  - references in struct field and any implementations
- beware: only ever used on references!
- type of generic
- static lifetime is duration of whole program





## Smart Pointer

?? stores data on the heap
- manages memory for you

pointer to a type
provides some behavior beyond a raw pointer
as transparent as possible through the Deref trait and deref coercion

extra metadata and capabilities

usually owns the value

String and Vec are smart pointers

struct that implements deref and deep traits
deref allows to coerce to reference, can write code for reference and works

?? implements drop trait, deallocates memory

### Box

??? Basic

reference to Box of Type can be coerced to reference to Type

allows to allocate value on the heap

not much extra functionality

can use when needs sized type but doesn't know size
can use when wants to transfer ownership of large value without copying it
can use wir trait object, dynamic?? polymorphism, specifies trait instead of concrete type

use e.g. for recursive enum

allows immutable or mutable borrows

### Rc

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

### Arc

Atomic Rc
Send and sync

like Rc, but thread safe, can pass to multiple threads

can use with mutex for shared ownership and mutability

### Weak

? like Rc, but doesn't own value

can create from Rc using `downgrade` method

can convert to Rc using `upgrade` method, returns some of value hasn't been dropped yet
? always needs to upgrade if wants to use

### RefCell

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
also can't ￼mutate mutabler value through immutable borrow

can solve with indirection, data structure (struct) holds mutable value, can mutate it internally through methods
gets immutable reference to data structure
"interior mutability pattern"

RefCell is fancy such data structure
but instead of mutation through methods
calls methods to get an im/mutable reference to value
RefCell checks at runtime that references are values

? can combine with Rc to get multiple owners of mutable value




## Raw pointer

??

ignore borrowing rules
can have immutable and mutable raw pointers, or multiple mutable raw pointers, to value
allowed to point to invalid memory, "be null"?, undefined behavior, compiler might not access memory or segmentation fault
don't implement any automatic cleanup

can convert reference to raw pointer using `as` cast??

can dereference only in unsafe block

### immutable

? can't be assigned after has been dereferenced

```rs
*const TYPE
```

beware: `*` isn't dereference operator

### mutable

? can be assigned after has been dereferenced

```rs
*mut TYPE
```

beware: `*` isn't dereference operator
