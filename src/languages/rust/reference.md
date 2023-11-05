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
- also calls shared for immutable, unique for mutable



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

- mutable reference can coerce to immutable reference

note, reference and value aren't equal, different types, e.g. `5 == &5`

can still create memory leaks with reference cycles, e.g. using Rc and RefCell
can maybe replace one Rc with Weak

weak pointer: doesn't own value
strong pointer??: owns value

?? fat pointer, pointer to start and length ?? Or only for slice

- mutability only through mutable reference
- disallows certain memory-safe scenarios that can't be checked at compile time
- can circumvent using Interior Mutability



## Dereference

- syntax of operator is leading star

### Coercion

- automatic dereferencing of smart pointer type
- type needs to implements `Deref` and `DerefMut` traits
- can think of inserting dereference operator
- beware: implicit, automagical ❗️
- allows to use type transparently like reference of contained type
- as many times as necessary, multiple
- resolves chain of types, cascades
- until type that doesn't implement `Deref`
- converts reference of type to reference of contained type
- beware: doesn't dereference last reference to primitive type ❗️
- allows to use reference to any wrapper type like reference of contained type
- best practice to accept reference of contained type to be most general
- e.g. `&String` for `&str`
- beware: ambiguity between methods on wrapper type and contained type, by convention use associated functions on wrapper type ❗️
- at compile time
- no performance penalty



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


not bound by borrowing rules
allows mutable and immutable references to a value at same time
also multiple mutable
can be null or point to invalid memory
not automatically cleaned up

can create by casting reference
immutable from immutable reference with `as *const T`
mutable from mutable reference with `as *mut T`

or by casting arbitrary memory address

immutable
can't be assigned after dereferenced

creation is safe
unsafe to dereference

used for
achieve greater performance
ability to interface with other languages￼
ability to build safe abstractions that the borrow checker doesn't understand ￼
to interface with hardware

### immutable

can't be assigned after dereferenced

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



## Function Pointer

- pointer to element of set of functions with given signature
- beware: not reference to function, not of specific unique anonymous type ❗️
- can think of pointer to block of code with a input-output signature instead of value of a type
- beware: can't create itself, instead gets from casting function or closure that doesn’t capture variables ❗️
- can call like function
- can use like function
- beware: don't confuse with specific anonymous unique function type ❗️
- has static lifetime
- implements all three closure traits `Fn`, `FnMut`, `FnOnce`
- can pass in place of closure
- beware: don't confuse with closure ❗️
- best practice to accept closure to be most general
- syntax is lowercase `fn`
- also called function signature, in contrast to specific unique anonymous function type



## Smart pointer

- owns value, dropped automatically when itself is dropped
- beware: only thinks of it when shared ownership ❗️
- statically sized
- reference is pointer to pointer
- best practice to use coercion target, avoids extra layer of indirection
- usually implements `Deref` trait
- usually doesn't implement `Copy` trait, since copying data on heap is expensive
- usually implements `Clone` trait



## Interior Mutability

- mutatability through immutable reference
- uses wrapping smart pointer that offers methods to read and mutate underlying value
- allows shared mutability
- beware: prefer inherited mutability through direct references, use only if necessary ❗️
can think of mutable memory location behind immutable pointer



## Resources

- [Ricardo Martins - Interior mutability in Rust: what, why, how?](https://ricardomartins.cc/2016/06/08/interior-mutability)
- [Code to the Moon - Rust Interior Mutability - Sneaking By The Borrow Checker](https://youtube.com/watch?v=HwupNf9iCJk)
