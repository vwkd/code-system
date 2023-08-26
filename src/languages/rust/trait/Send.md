# Send



## Introduction

- type is safe to send between threads
- automatically implemented, unless contains type that isn't `Sync`
e.g. if contains `Rc<..>`, could use `Arc<..>` instead
- automatically imported because included in prelude



## Resources
