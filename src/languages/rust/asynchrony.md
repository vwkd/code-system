# Asynchrony



## Introduction

async await
special syntax
pause execution
yield control back to the runtime
other code can make progress
then pick back up later where left off
can write async code that looks like sync code

async keyword is syntax sugar for returning impl Future ???with associated type Output






enables concurrency

similar to JavaScript
Future is Promise
async await syntactic sugar

but lazy instead of eager
start execution only once awaited, not once created

multiple threads offer true parallelism instead of only single-threaded concurrency via event loop

std library provides only OS threads, third party crates for green threads
spawn takes closure function

if main thread ends, all spawned threads end too, no matter if ended or not
wait for spawned threads in main thread by calling `handle.join()`
join blocks main thread until spawned thread terminates
beware: use join at end of main otherwise main thread blocks!

? closure must not depend on outer state, since doesn't know how long lives, can't coordinate cleanup
? must use `move` to move ownership of variables inside closure

can transfer data between threads by message passing
std library offers channels std::sync::mpsc
use move closure that takes ownership of transmitter
try_recv takes message if available, recv blocks thread until message is available
send takes ownership of value, moves it to other thread
can iterate over receiver, gets new message each iteration
can clone transmitter, pass to second thread, has multiple transmitters

transfer data by shared state using mutex (mutual exclusion)
only one thread at a time can access value
thread acquires lock, accesses value, releases lock
harder to work with because of lock
mutex lock is smart pointer
  - implements deref trait, dereference value
  - implements drop trait, releases lock at end of scope, automatically
for multiple threads can wrap mutex in Arc
mutex uses interior mutability
beware: risk of deadlocks

send and sync traits??



## Resources
