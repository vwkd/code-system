# Variable



## Introduction

- name of a value
- value can be on stack or on heap
- stored itself on stack
- identifier is bound to memory address of value
- allows to read and write value
?? if writes to variable, changes variable to point to new address in memory or overwrites value at address in memory



## Derivation

- creation of new variable based on existing variable
- e.g. assignment, function call, function return, etc.
- either copies or reuses underlying value
- beware: own term, not sure if there's an official term ❗️



## Scope

- part of program where is valid
- can be lexical or dynamic

### Lexical

- region of code
- e.g. other function doesn't have access to scope of function where called from because is other region of code
- can have gaps, holes
- common

### Dynamic

- region of execution path
- can also think of period of execution time
- e.g. other function has access to scope of function where called from because it is still running
- can't have gaps, holes
- uncommon



## Lifetime

- time during which is valid
- also called extend
- beware: also often means part of scope where is actually valid ❗️

### Lexical

- equal to corresponding scope

### Non-lexical

- shorter or equal to corresponding scope
- e.g. creation to last use



## Resources
