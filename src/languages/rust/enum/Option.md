# Option



## Introduction

- represents value or not
- replaces null in other languages
- forces null handling
- in standard library
- automatically imported because included in prelude

implements `IntoIterator`, can be iterated over, has either 0 or 1 elements

unwrap method to panic at runtime, can use during development or when case never happens

? question mark operator also works, extracts Some or returns None

? has map method that maps some of some otherwise just back to none

never use &Option<T>, always Option<&T>

can convert to Result with `ok_or(())`

special case of Result, only one self-explanatory reason of saying missing value



## Resources

- [Logan Smith - Code the Right Option](https://youtube.com/watch?v=6c7pZYP_iIE)
