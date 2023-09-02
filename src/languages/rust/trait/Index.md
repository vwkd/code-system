# Index & IndexMut



## Introduction

- ability to index
- may panic if index is out of bounds



## Index

- if immutable value requested
- `index` method
- `container[index]` is sugar for `*container.index(index)`
- type  of value must implement `Copy`
- beware: can't index non-`Copy` element, because would move out, leave invalid "gap" ❗️



## IndexMut

- if mutable value requested
- `index_mut` method
- `container[index]` is sugar for `*container.index_mut(index)`



## Resources
