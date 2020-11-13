# Rust

[TOC]

<!-- ToDo: finish -->

## Introduction

<!-- ?? -->

- expression based language: `if`, loops, blocks are expressions


## Variables

variables point to area in memory
?? if writes to variable, changes variable to point to new address in memory or overwrites data at address in memory
function parameters are actually just variables, get assigned the function parameters

### Variables

can be shadowed
type is inferred ??
value can be computed expression ?? needs type then ??
can not be declared in any scope, e.g. global scope ??
snake case by convention

### Constants

can't be shadowed
type needs to be specified
value can only be constant expression, not computed
can be declared in any scope, including global scope
upper case by convention



## Ownership

value has single owner (variable)
value is dropped when owner goes out of scope

when assigns variable with complex type to another, first is invalidated, can't use anymore, nothing happens when moves out of scope
    new variable is now owner, memory of value is freed when variable goes out of scope

reference is pointer to variable on stack, allows to use value without taking ownership of it, can write to it by making reference mut
    therefore only works while variable is in scope
    doesn't drop value when reference goes out of scope since is not owner
    "borrowing": references as function parameters
    can have mutiple non-mutable references to a value per scope or a single mutable reference, prevents data races
    scope of a reference starts with definition and ends with last use, smaller or equal than variable scope !!! i.e. can't have dangling pointers since reference is always out of scope before variable and therefore memory is freed
    was introduced for easier manipulation of a variable, to not have to transfer ownership into a function and return it again