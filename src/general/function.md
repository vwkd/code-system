# Function



## Introduction

- reusable part of code
- takes input and gives output
- relation between input and output
- has parameters and return value
- has signature
- can be first-order or higher-order
- can be impure or pure
- can be combinator



## Parameter

- input in function definition
- variable that the argument is assigned to
- think of variable assignment when connecting two parts of code

### Arity

- number of parameters
- unary: one
- binary: two
- n-ary: n



## Argument

- input in function call
- assigned to parameter



## Return value

- output from function call
- assigned to call site

### Dimension

- number of return values



## Signature

- general type of function with parameters and return type
- beware: not specific unique function type ❗️



## First-order

- doesn't take functions as arguments and doesn't return new function
- not higher-order



## Higher-order

- takes other functions as arguments and/or returns new function as result
- operates on functions
- can think of function of functions
- combines functions
combines, manipulates, transforms functions into new function
- also called functional, operator
- needs first-class functions



## Impure

- output depends not only on input
- can have side effects
- not pure
- note: non-local variable doesn't necessarily make impure, could be constant



## Pure

- output depends only on input
- can't have side effects
- i.e. given same input always produces same output
- predictable, since provable effect
- more efficient, since runtime can optimize
- e.g. run in parallel, "memoize" return values for further invocations, etc.
- best practice to minimize and contain impurities as much as possible
- calling an impure function makes function itself impure
- beware: every function above first impure function in call tree is impure ❗️



## Combinator 

- higher-order pure function for a single task that can chain
- makes operations declarative and modular
- usually implemented as method on algebraic data type that returns new instance of same type
- e.g. forEach, map, filter, sort, reduce, etc.



## Resources
