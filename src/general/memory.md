# Memory



## Introduction

- ability to store data
- volatile or persistent
- note: value calls specific data, data calls unspecific values ❗️



## Persistent

- using hard drive
- slow
- abundant
- persist without power, after shutdown
- used to persist data



## Volatile

- using RAM
- fast
- scarce
- lost without power, after shutdown
- used to execute programs
- beware: in programming languages usually refers to volatile, not persistent, e.g. "memory management"!
- three regions: static, stack and heap

### Static

- stores
  - program binary
  - static variables
  - string literals
- fixed size, known at compile time
- values lifetime as long as lifetime of program
- cleanup automatic when program terminates

### Stack

- stores state of functions
- made up of a stack frame for each function
- creates stack frame when calls function, pops off when returns, like stack of plates, LIFO
- stack frame
  - fixed size, known at compile time
  - stores
    - arguments
    - local variables
    - beware: sizes must be known at compile time, since stack frame size must be known at compile time!
  - values lifetime as long as lifetime of function
  - cleanup automatic when function returns
- dynamic size, can grow, but fixed upper limit, stack overflow
- each thread has its own stack
- beware: full name "call stack", but often shortened to "stack"!

### Heap

- stores
  - values that live beyond function lifetime
  - values accessed by multiple threads
  - large values that could exceed stack size
  - values with unknown size at compile time
- dynamic size, can grow, upper limit is memory size
- all threads share same heap
- values lifetime not predefined, determined by programmer, "de/allocation"
- cleanup is manual, by programmer
- memory management strategies automatic or manual
- beware: "memory management" usually refers to management of heap!
- beware: mismanagement is large source of memory bugs and security vulnerabilities!
- must use behind some sort of reference

#### Manual

- by programmer
- full control, efficient
- tedious, error prone, unsafe
- e.g. C

#### Semi

- efficient
- semi-tedious, safe
- resource acquisition is initialization (RAII)
- ownership based resource management (OBMM)
- e.g. C++ (RAII), Rust (OBMM)

#### Automatic

- by runtime, garbage collector, pauses program every time to do cleanup
- no control, inefficient
- easy, error free, safe
- e.g. JavaScript



## Endianness

- order of bytes in multi-byte value
- e.g. in memory, in communication channel, etc.
- beware: nothing to do with physical layout ❗️
- beware: in examples often implicitly assumes positions grow left-to-right like text, low is left, high is right ❗️

### Big

- most significant byte at lowest position, least significant byte at highest
- dominant in network protocols, e.g. IP
- "big first"

### Little

- least significant byte at lowest position, most significant byte at highest
- dominant in processor architectures, e.g. x86, ARM, RISC-V
- "little first"



## Resources

- [Let's Get Rusty - Stack, Heap, and Static Memory](https://youtube.com/watch?v=NnLdGKoz1ls)
- [Let's Get Rusty - Memory Management Strategies](https://m.youtube.com/watch?v=GUZ_2gGWuPo)
