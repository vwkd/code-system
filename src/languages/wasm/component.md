# Component



## Introduction

- composable Wasm module
- enables capability-based, virtualizable interface



## Wasm Interface Type (WIT) format

- IDL
- naming is kebab-case, ASCII-only
- written in `.wit` files
- beware: single `.wit` file doesn't necessarily correspond to single component ❗️

### Interface

- set of types and functions
- can think of instance type
- can think of unit of functionality
- can import types and functions from other interfaces
- has single namespace, defined names must not collide

### World

- set of imports and exports
- can think of component type
- can contain functions and interfaces
- can think of set of functionalities
- can import and export same foreign interface by ID, but not local interface

### Package

- set of interfaces and worlds
- `.wit` files in the same directory
- order of interfaces and worlds in `.wit` files doesn't matter
- has id from namespace, name and optional semver version
- id `namespace:name@version` at top of at least one `.wit` file
- can't have cyclical references between interfaces



## Resources

- [Component Model design and specification](https://github.com/WebAssembly/component-model/tree/d1f47566f7aa9c8ab7bae2826eb9d123b2196512)
- [The `wit` format](https://github.com/WebAssembly/component-model/blob/d1f47566f7aa9c8ab7bae2826eb9d123b2196512/design/mvp/WIT.md)
