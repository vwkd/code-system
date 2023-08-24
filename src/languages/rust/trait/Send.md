# Send



## Introduction

type is safe to send between threads
automatically implemented, unless contains type that is not safe to send
e.g. if contains `Rc<..>`, could use `Arc<..>` instead



## Resources
