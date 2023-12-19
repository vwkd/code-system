# Data Type



## Introduction

- set of values
- can be primitive or non-primitive
- can be scalar or composite
- can be non-collection or collection
- can be statically or dynamically sized
- can be zero sized
- can be algebraic
- can be generic, associated
- can be sub or super
- beware: name is also used for a value ❗️



## Primitive

- built-in
- defined by language



## Non-primitive

- not built-in
- defined by user



## Scalar

- value is atomic



## Composite

- value consists of other values
- also called compound



## Non-collection

- value consists of single value
- usually scalar
- single value in memory
?? no proper term



## Collection

- value consists of multiple values
- usually composite
- beware: not necessarily contiguous sequence of values in memory ❗️



## Statically sized (SST)

- size known at compile time
- also called sized
- beware: don't confuse with fixed or dynamic size, if can grow or shrink ❗️



## Dynamically sized (DST)

- size only known at runtime
- also called unsized, not sized
- must use behind some sort of reference
?? has extra bit of metadata that stores size of data
- e.g. recursive type
- beware: don't confuse with fixed or dynamic size, if can grow or shrink ❗️



## Zero sized (ZST)

- occupies no space
- optimized away
- has single unique value



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
- also called type parameter



## Associated

- type alias associated with another type
- represents single concrete type
- can think of placeholder



## Sub

- subset of other type
- writes `T <: S` for other type `S`



## Super

- superset of other type
- writes `T :> S` for other type `S`



## Coercion

- conversion of one type into another type
- usually automatic, implicit



## Resources
