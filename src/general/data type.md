# Data Type



## Introduction

- set of values
- can be primitive or non-primitive
- can be scalar or composite
- can be non-collection or collection
- can be statically or dynamically sized
- can be algebraic
- can be generic, associated



## Primitive

- built-in



## Non-primitive

- not built-in



## Scalar

- not made up of other types
- atomic



## Composite

- made up of other types
- also called compound



## Non-collection

- stores single value
- usually scalar
?? no proper term



## Collection

- stores multiple values
- usually composite



## Statically sized (SST)

- size known at compile time
- size is fixed
- also called sized



## Dynamically sized (DST)

- size only known at runtime
- size can grow and shrink
?? has extra bit of metadata that stores size of data
- must use behind some sort of reference
- also called unsized



## Algebraic (ADT)

- composite from algebraic operation
- can be sum or product
- used to model complex data types
- can think of custom data type
- beware: in programming often called just "type" ❗️

### Sum

- from sum operation
- constituent types are called variants
- is any one of its variants
- e.g. union, enum, etc.
- possible values is sum of possible values of variants
- used to represent options, alternatives, etc.

### Product

- from product operation
- constituent types are called fields
- is group of its fields
- e.g. tuple, record, etc.
- possible values is product of possible values of fields
- used to represent combinations, groups, etc.



## Generic

- abstract data type
- represents multiple concrete data types
- enables polymorphism



## Associated

- type alias associated with another type
- represents single concrete type
- can think of placeholder



## Coercion

- conversion of one type into another type
- usually automatic, implicit



## Resources
