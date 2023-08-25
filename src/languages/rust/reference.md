# Reference



## Introduction

- safe, has rules and restrictions
- doesn't take ownership of value, doesn't own value, remains owned by other variable
- also called "borrow", creation of reference "borrowing"
- syntax is leading ampersand before variable or type
- immutable by default
- can declare mutable only if variable is also mutable
- to use owned value in outer scope needs to return it, can't return reference since would be dangling pointer



## Rules

- can either have one mutable reference or any number of immutable references
- prevents data races
- references must always be valid
- lifetime must be smaller than variable it references
- prevents dangling pointer
- prevents null pointers
- when it goes out of scope nothing happens, value is not dropped
- scope is between declaration and last use, "non-lexical lifetime"
- beware: scope is smaller than variable scope ❗️

```rs
// `s1` scope start
let mut s1 = String:from("LGR");
// `r1` scope start
let r1 = &s1;
// `r1` scope end
// `r2` scope start
let r2 = &mut s1;
println!("{r2}");
// `r2` scope end
// `s1` scope end
```

- can't use existing variable in meantime??

mutable reference coerces to immutable reference

note, reference and value aren't equal, different types, e.g. `5 == &5`

can still create memory leaks with reference cycles, e.g. using Rc and RefCell
can maybe replace one Rc with Weak

weak pointer: doesn't own value
strong pointer??: owns value

?? fat pointer, pointer to start and length ?? Or only for slice



## Dereference

- syntax of operator is leading star
- automatic dereferencing



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

can use underscore to infer single lifetime since uniquely determined, "anonymous lifetime" ?? STILL NECESSARY WITH NEW COMPILER
underscore also used to ignore lifetime in argument ?? very confusing if used in return type to, since same symbol but not same lifetime
e.g. `fn foo(x: &str, y: &'_ str) -> &'_ str { x }`

can specify that one lifetime lives at least as long as other, like trait bound ??? `<'newLifetime: 'existingLifetime>`

?? like subtypes



## Smart Pointer

?? stores value on the heap
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
