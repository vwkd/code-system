# Reference



## Introduction

- safe, has rules and restrictions
- doesn't take ownership of value, doesn't own value, remains owned by other variable
- also called "borrow", creation of reference "borrowing"
- syntax is leading ampersand before variable or type
- immutable by default
- can declare mutable only if variable is also mutable
- to use owned value in outer scope needs to return it, can't return reference since would be dangling pointer
- lifetime is shorter or equal to lifetime of borrowed value



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



## Mutability

### Inherited

- mutability only through mutable reference
- can mutate value only if declared mutable
- prefer when possible

### Interior

- mutability through immutable reference
- beware: can mutate value even if declared immutable ❗️
- last resort
- used to mutate inside of immutable type, e.g. `Rc`, `Arc`, etc.
- used to mutate through `clone` method



## Dereference

- syntax of operator is leading star
- type needs to implement `Deref` and `DerefMut` traits

### Coercion

- automatic dereferencing 

??? only one reference to other
not to last underlying value

- converts reference of one type to reference of other type

- allows to use reference to wrapper type like reference to regular type, e.g. smart pointer
in same place as
- allows to implement only for reference to regular type and use with reference to wrapping type, e.g. `&str` instead of `&String`

- can think of adding deref operators automatically
- as many times as possible
- resolves chain of references, cascades

- beware: implicit, automagical ❗️

- at compile time
- no performance penalty

- coerces im/mutable reference to immutable, mutable to mutable
- beware: not mutable reference to immutable reference, would break borrowing rules ❗️

allows to treat type the same as reference, use in same places, e.g. with dereference operator

ambiguity if containing type also defines methods
by convention use functions rather than methods

- automatically applies the `*` operator to values of types that implement the `Deref` trait
- allows using methods and fields of the target type directly on values of the source type that implements `Deref`.
- follows a chain of types that implement `Deref` until it reaches a type that doesn't implement `Deref`
- beware: doesn't dereference last step down to primitive values or non-reference types, needs to manually dereference ❗️



## Lifetime specifier

- description of relationship between lifetimes

- beware: only for reference ❗️
- beware: doesn't change actual concrete lifetime, no runtime effect, only satisfy type checking ❗️
- also called generic lifetime annotation
- beware: often just called lifetime, don't confuse with actual concrete lifetime ❗️

- lifetime is inferred when possible
- for function the lifetime of single reference parameter is assigned to all references in the return value
- for borrowing method the lifetime of self is assigned to all references in the return value
- can elide when inferred, otherwise needs to specify

- syntax of declaration like generic, leading tick, by convention lowercase
- syntax of use behind ampersand of reference
- can use placeholder lifetime underscore to make explicit that it's inferred

///

minimum lifetime
can assign any same type with longer lifetime
- minimum lifetime of input reference, maximum lifetime of output reference
- specified as another reference lifetime
- ??usually output reference lifetime 
- specifies minimum lifetime of output reference is at least lifetime of input reference, not exact same lifetime

underscore also used to ignore lifetime in argument ?? very confusing if used in return type to, since same symbol but not same lifetime
e.g. `fn foo(x: &str, y: &'_ str) -> &'_ str { x }`

can specify that one lifetime lives at least as long as other, like trait bound ??? `<'newLifetime: 'existingLifetime>`

?? like subtypes

///

-> can use immutable and mutable references in same scope, as long as lifetimes don't overlap

lifetime of return value is equal to shortest lifetime passed in

if returns reference
lifetime of return value must be tied to lifetime of input parameters
because reference to owned value inside function would be invalid since dropped at return
except for static lifetime
can return value with static lifetime instead since lives at least as long

e.g. reference return value of function with multiple reference arguments
e.g. reference in struct, also in implementation block

when same GLA for multiple input lifetimes takes on shortest concrete input lifetime



## Smart Pointer

- usually struct
- usually implements `Deref` and `Drop` traits
- usually owns value
?? stores value on the heap



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
