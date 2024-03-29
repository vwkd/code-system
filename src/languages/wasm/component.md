# Component



## Introduction

- composable module
- builds on top of core module
- has standardised ABI
- beware: can't export memory unlike core module ❗️
- enables capability-based, virtualizable interface



## Wasm Interface Type (WIT) format

- IDL
- identifiers are ASCII letters and digits, kebab-case, each word either all upper- or lowercase
- identifier with leading `%` escapes WIT keywords
- beware: no Unicode ❗️
- written in `.wit` files
- beware: single `.wit` file doesn't necessarily correspond to single component ❗️

### Interface

- set of types and functions
- can think of instance type
- can think of unit of functionality
- can import from other interfaces
- has single namespace, defined names must not collide

### World

- set of interfaces that imports and exports
- ? can also import/export inline functions, but can't compose with other components, only use with host
- can think of component type
- can think of set of functionalities
- can both import and export same interface only if foreign, using `package/interface`
- beware: corresponds to single component ❗️

### Package

- set of worlds and interfaces
- `.wit` files in the same directory
- order of interfaces and worlds in `.wit` files doesn't matter
- has id from namespace, name and optional semver version
- id `namespace:name@version` at top of at least one `.wit` file
- can't have cyclical references between interfaces
- beware: doesn't necessarily correspond to single component ❗️



## Resources

- [Component Model design and specification](https://github.com/WebAssembly/component-model/tree/d1f47566f7aa9c8ab7bae2826eb9d123b2196512)
- [The `wit` format](https://github.com/WebAssembly/component-model/blob/d1f47566f7aa9c8ab7bae2826eb9d123b2196512/design/mvp/WIT.md)
- [The WebAssembly Component Model](https://component-model.bytecodealliance.org/)
