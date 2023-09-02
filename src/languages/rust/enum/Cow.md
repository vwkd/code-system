# Cow



## Introduction

???

 allows to conditionally either borrow data or own it
 that dynamism takes place at runtime
  essentially an enum of `Vec` and `&[T]` (in this case). 
  has a borrow type inside it
  it comes with the source code overhead of needing lifetime parameters everywhere
  doesn't allow to make shallow-but-owned copies like Arc does
  
  can eliminate unnecessary deep clones
  but not a drop-in replacement for Vec, unlike Arc<[T]> can be



## Resources
