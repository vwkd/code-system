# Error



## Introduction

- recoverable error with types
- unrecoverable error called panic
- seldom
- no exceptions and try catch



## Custom enum

- complex, needs to map
- user can distinguish error
- should implement `Error`, `Display` and `Debug`

## Trait object

- simple, can just return
- user can't distinguish error



## Question mark operator

- for Result unwraps Ok or returns Error
- for Option unwraps Some or returns None

?? automatically converts into target if implements `From` trait



## Resources
