# Introduction

<!-- ToDo: finish -->

<!-- todo: explain segfault, race conditions -->
<!-- todo: explain runtime, garbage collection -->


## Terminology

- statement: unit of code that performs some action, doesn't return a value (returns empty value), e.g. variable definition, function definition, etc.
- expression: unit of code that evaluates to a value, e.g. `1 + 2`, function call, etc.



## Memory

data is just 1s and 0s at a certain memory address
in system level language manages memory yourself, needs to write and delete data in memory
    but good compiler may analyse and write cleaning part for you, e.g. rust
in higher level language runtime does the cleaning
but where is kernel and OS in between, how is memory assigned, etc.???

code is compiled to binary ?? run directly on CPU ??
but where is kernel and OS in between, process, etc. ??

what is garbage collection? program injected by compiler that cleans up unused memory at runtime?
alternative would be to allocate and free manually
    or let smart compiler do it, if language can guarantee safety, e.g. Rust
only needed for data on the heap? not needed for stack?!
beware: by memory usually refers to heap, not stack, although all lives in memory

??What is a (mutable) reference? Not a pointer itself!?!?! since every variable is a pointer ?! --> POINTER TO VARIABLE
nyes, a primitive type is on the stack, a variable just points to the stack
      a complex type is on the heap, has a pointer on the stack, a variable points to the pointer on the stack
??? OR IS VARIABLE ITSELF ACTUALLY STORED ON THE STACK, MEANING FOR PRIMITIVE TYPE THE VARIABLE IS A PROPERTY OF THE ENTRY ON THE STACK??

size needed for stack is known after compile, maximum size of data that lived at same time
size of heap is variable?? adapts ??

Stack is LIFO queue, holds variables etc., pushes on stack when in scope and pops off when out of scope
    e.g. in function since creates a scope

simple type: value stored on stack, immutable, fixed size
complex type: value stored on heap, mutable, growable size
beware: can have same kind of values in both types, e.g. strings in Rust can be simple or complex

allocate memory -> use memory -> release memory
memory a leak, when release does not happen

IN JS
forgotten global variables, forgotten timers, forgottenx references to deleted DOM nodes



## Resources

- [Steve Klabnik, Carol Nichols - The Rust Programming Language](https://doc.rust-lang.org/book/)