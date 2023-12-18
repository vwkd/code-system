# Into



## Introduction

- ability to convert to target type `T`
- opposite of `From`
- consumes owned value
- must not fail, for failure see `TryInto`
- not necessarily cheap
- automatically implemented if implements opposite `From`
- beware: don't manually implement, instead implement `From` and use automatic implementation ❗️
- beware: don't use anymore, exists because historically orphan rules were more strict ❗️



## Resources
