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
- writes `F<T>` for a component type `T`
- beware: component doesn't need to be explicit generic, can be implicit ❗️



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
- beware: don't confuse with fixed or dynamic size of collection, if can grow or shrink ❗️



## Dynamically sized (DST)

- size only known at runtime
- also called unsized, not sized
- must use behind some sort of reference
to make statically sized
?? has extra bit of metadata that stores size of data
--> not necessarily, e.g. trait object
stores pointer to type and also stores pointer to vtable for the trait
--> not necessarily, e.g. slice
- e.g. recursive type
- beware: don't confuse with fixed or dynamic size of collection, if can grow or shrink ❗️



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
- if generic over `T` inherits variance from constituent types using `T`
  - covariant in `T` if all constituent types using `T` are covariant
  - contravariant in `T` if all constituent types using `T` are contravariant
  - otherwise invariant in `T`

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

- abstract supertype
- represents multiple concrete subtypes
- enables polymorphism
- also called type parameter
- beware: sometimes also calls composite type itself ❗️



## Associated

- type alias associated with another type
- represents single concrete type
- can think of placeholder



## Sub

- subset of other type
- writes `T <: S` for other type `S`
- can use in place of supertype



## Super

- superset of other type
- writes `T :> S` for other type `S`
- can use subtype in place of itself



## Variance

- relationship of component subtyping to composite subtyping
- how subtyping of component type affects subtyping of composite type
- beware: not necessarily same for multiple components of composite type ❗️
- beware: can quickly get confusing for nested composite types `G<..<F<T>>..>` ❗️
- assuming `T <: S`, then

### Covariant

- preserved subtype ordering, same subtyping
- varies in same direction
- `F<T> <: F<S>`
- e.g. list in element type, function in return type

### Contravariant

- reversed subtype ordering, opposite subtyping 
- varies in opposite direction
- `F<S> <: F<T>`
- e.g. function in argument type

### Bivariant

- both covariant and contravariant
- `F<S> = F<T>`

### Invariant

- no subtype ordering
- doesn't vary
- no subtyping relationship between `F<T>` and `F<S>`
- also called not variant



## Coercion

- conversion of one type into another type
- usually automatic, implicit



## Resources
