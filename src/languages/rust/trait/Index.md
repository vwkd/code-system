# Index & IndexMut



## Introduction

- ability to index
- index can be range
- index can be dynamic
- may panic if index is out of bounds
- copies element
- type of value must implement `Copy`
- beware: for non-`Copy` type can't index element, because would move out, leave invalid "gap" ❗️



## Index

- if immutable value requested
- `index` method
- `container[index]` is sugar for `*container.index(index)`



## IndexMut

- if mutable value requested
- `index_mut` method
- `container[index]` is sugar for `*container.index_mut(index)`



## Resources
