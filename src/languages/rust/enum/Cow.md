# Cow



## Introduction

- smart pointer
- allows clone-on-write, dynamically allocate only on modification
- contains reference to value
- implements `Deref` to get reference
- method `to_mut` clones value and stores owned value instead, gives mutable reference
- beware: doesn't implement `DerefMut` to make allocation explicit ❗️



## Resources
