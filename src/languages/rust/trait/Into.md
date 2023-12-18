# Into



## Introduction

- ability to convert to target type `T`
- like `From`, but opposite
- automatically implemented if implements `From`
- beware: don't manually implement, instead implement `From` and use automatic implementation ❗️
- beware: doesn't need, historical origins when orphan rules were sometimes too strict to implement `From` ❗️
- beware: use only for syntactic convencience over `From::from` ❗️



## Resources
￼