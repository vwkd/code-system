# Deref & DerefMut



## Introduction

?? coerce to reference
allows to treat type the same as reference, use in same places, e.g. with dereference operator

opt in to coercion

associated type `target`
not a type parameter since each “smart pointer” should only ever be dereferenceable to a single other type

?? also customizes behavior of deference operator
allows to be used with dereference operator
because will coerce to reference which knows how to dereference

implicit deref coercion automagically
?? on function call
cascades until last, e.g. &Box<String> -> &String -> &str
for im/mutable reference of one type to immutable reference of other type, and for mutable to mutable

note: `.deref()` bad method name, because only converts to reference, the actual dereferencing is done in the deref coercion (regardless of Deref)



## Resources
