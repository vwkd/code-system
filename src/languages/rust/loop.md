---
title: Loop
index: ???
---



## Introduction

???
- repeating part of code
- can break with `break` statement, can return value, defaults to unit
- can label ancestor loop, identifier must start with tick, can break out of ancestors loop using label



## for loop

- loop through collection
irrefutable pattern

- just sugar for iteration using `.into_iter()`
- iterable can be owned, reference or mutable reference type
- loops until iterator returns `None`
- can think of `while` loop

```rs
let iter = IntoIterator::into_iter(iterable);
while let Some(value) = iter.next() { 
  // ... do something with `value`
}
```

- actually becomes `loop` with `break`
- outer `match` prevents dropping any temporary values before end of loop
- declares `value` before being assigned because more often correctly infers types

```rs
let result = match IntoIterator::into_iter(iterable) {
  mut iter => loop {
    let mut value;
    match iter.next() {
      Some(next_value) => value = next_value,
      None => break,
    };
    {
      // ... do something with `value`
    }
  },
};
```



## while loop



## `while let`

ir/refutable pattern
but warning if irrefutable since wouldn't need it

- loop as long as one value
pattern matches
