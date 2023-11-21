# Component Model



## Introduction

- standard for composition of Wasm modules
- enables capability-based, virtualizable interfaces



## Wasm Interface Type (WIT)

- IDL for Component Model

describe the imports and exports to a component

`.wit` file can contain multiple worlds
beware: single `.wit` file doesn't necessarily correspond to single component!

### Package

- set of interfaces and worlds
- defined in files in the same directory that all use the file extension `wit`

basis of sharing types and definitions in an ecosystem of components

Types can be imported between interfaces within a package and additionally from other packages through IDs.

A "package" groups together a set of interfaces and worlds that would otherwise be named with a common prefix.

can be defined in a collection of files and at least one of them must specify a package name. Multiple files can specify a package and they must all agree on what the package name is.

can contain any number of interfaces listed at the top-level and in any order
all references between interfaces must be well-formed and acyclic

can contain world definitions at the top-level in addition to interface definitions.

group definitions, don't represent behaviour

- has id of namespace, name and optional semver version
id at the top of a WIT file via a package declaration
used to generate the names of imports and exports of interfaces and worlds

### Interface

- set of types and functions
- can think of as instance type
- can think of unit of functionality
- can contain use statements, type definitions, and function definitions
- has single namespace, defined names must not collide

### World

- set of imports and exports
- can think of as component type
- can contain functions and interfaces
- can think of set of functionalities

plain name of import or export statement becomes plain name of final component import or export definition

Kebab names cannot overlap and must be unique, even between imports and exports.
IDs, however, can be both imported and exported.
same interface cannot be explicitly imported or exported twice.



## Resources

- [Component Model design and specification](https://github.com/WebAssembly/component-model/tree/d1f47566f7aa9c8ab7bae2826eb9d123b2196512)
- [The `wit` format](https://github.com/WebAssembly/component-model/blob/d1f47566f7aa9c8ab7bae2826eb9d123b2196512/design/mvp/WIT.md)
