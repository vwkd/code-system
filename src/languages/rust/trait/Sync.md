# Sync



## Introduction

- marker trait
- ability to transfer reference across threads
- safe to send reference of type across threads
- iff reference of type is `Send`
- automatically implemented, unless contains type that isn't `Sync`
- automatically imported because included in prelude



## Resources
