# Process



## Introduction

??

usually a program runs in a process
managed by OS

owns resources, e.g. memory, file handles, sockets, device handles, etc.

isolated
expensive



## Thread

unit of kernel scheduling
lightweight

share resources of process

? process can contain many threads
? run concurrently
program doesn't know exact execution order of its parts, parts need to be independent
execution order is non-deterministic, might change with each run
beware: makes it hard to reproduce bugs!

race condition if two threads access data or resources in inconsistent order ??

deadlock if two threads wait on each other for freeing a resource that the other has, infinite wait

### Kernel thread

OS implementation of threads
created by calling OS API
map one-to-one to OS thread

also called OS threads, native threads, system threads, one-to-one threads, etc.

### User thread

programming language's own implementation of threads
created by calling programming language's own API
map m-to-n to OS thread, where m>=n

also called green threads, program threads, etc.

tradeoff is larger runtime that provides it
