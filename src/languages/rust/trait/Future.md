# Future



## Introduction

- lazy
- zero-cost abstraction


////2

state machine
with as many states as awaits + 1
can think of enum with states as variants
when polls future, runs first state (until first await)
future returns pending because waits for nested future to finish
once nested future is ready, future calls wake callback to notify executor that ready to make more progress
executor polls future again, runs second state
future returns pending
...
after running last state, future returns ready variant

can await only on async function or block

can't make main async

can drive future to completion by calling .await, or manually polling until it's complete
.await only works in nested async functions
top-most future needs some code that polls it to completion
runtime / executor
also runs multiple in parallel
rust doesn't have async runtime built-in built-in
most popular third party async runtime tokio

since future is lazy, can save return type of async function
and later call .await

single future is lazy, is ready to cancel
simply stop polling the future, don't await it

///1

associated type Output
function poll, check if it can return a value
returns Poll enum, either Ready with value or Pending because not done executing
accepts callback function `wake`

if poll returns pending, future makes progress until is ready to get polled again
if ready to get poked again, calls wake callback to notify its executor

lazy, won't do anything until driven to completion by being polled

can drive to completion by
either awaiting future
or giving it to executor

async function call returns future 
.await to future attempts to run it to completion
-> async code that looks sync
.await also pauses current future, yields control back to runtime





## Resources
