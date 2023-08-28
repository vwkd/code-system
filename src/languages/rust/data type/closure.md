# Closure



## Introduction

- anonymous function expression
- can capture variables of outer scope
- can think of outer variables like invisible function parameters
- more overhead than function because of closure
- automatically implements closure traits
- anonymous unique type
- beware: can't specify concrete type, instead specify generic with closure trait bound, accepts any closure that satisfies it ❗️



## Declaration

- optional signature type annotation
- infers from first use
- beware: input and output types are concrete, can't use generics ❗️
- immutably borrows, mutably borrows, or takes ownership of captured variables
- infers from use of captured variables
- can force taking ownership using `move` keyword
- beware: all captured variables have same ownership, can't borrow some mutably and others immutably ❗️
- automatically implements closure traits corresponding to use of captured variables



## Usage

- if struct field needs to wrap name in parentheses when calls



## Resources
