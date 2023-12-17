# Into



## Introduction

<!-- todo: ??? should not exist -->

- ability to convert to target type `T`
- opposite of `From`
- consumes owned value
- must not fail, for failure see `TryInto`
- not necessarily cheap
- beware: no automatic implementation of opposite `From` ❗️
- beware: don't manually implement, instead implement `From` and use automatic implementation ❗️



## Resources
