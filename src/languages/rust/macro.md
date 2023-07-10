---
title: Macro
index: ???
---

## Introduction

code which writes other code
like function whose input is code and output is other code

enables meta programming

runs during compile time
generates or modifies other code

allow to define custom syntax

hygienic
variables and identifiers are scoped to macro, don't clash with surrounding scope

can accept variable number of parameters
function which must declare fixed number of parameters

can pass different types as parameters

expanded at compile time
functions are called at runtime

declarative or procedural



## Declarative

matches against pattern

most widely used form

vec!

defined like match expression
maps input patterns to match arms

different pattern syntax than in match expression



## Procedural

takes code as input, produce code as output

custom-derived
attribute-like
function-like

defined like function, takes token stream and returns token stream



## Println

?? takes argument by reference even if not specified? `println!("{}", foo.bar)`