# Component Model



## Introduction


broad-reaching architecture for building interoperable Wasm libraries, applications, and environments



portable, load- and run-time-efficient binary format for separately-compiled components built from WebAssembly core modules that enable portable, cross-language composition.

Support the definition of portable, virtualizable, statically-analyzable, capability-safe, language-agnostic interfaces, especially those being defined by [WASI].



defines
grammar of types that can be used in WASI interfaces;
linking functionality that WASI can assume is used to compose separate modules of code, isolate their capabilities and virtualize WASI interfaces;
core wasm ABI that core wasm toolchains can compile against when targeting WASI.


like OS's process model (defining how processes start up and communicate with each other)


## Wasm Interface Type (WIT)

- IDL for Component Model

format to describe the imports and exports to a component

`.wit` file can contain multiple worlds
beware: single `.wit` file doesn't necessarily correspond to single component!

### Package

basis of sharing types and definitions in an ecosystem of components

- a collection of interfaces and worlds
- defined in files in the same directory that all use the file extension `wit`

Types can be imported between interfaces within a package and additionally from other packages through IDs.

A "package" groups together a set of interfaces and worlds that would otherwise be named with a common prefix.

can be defined in a collection of files and at least one of them must specify a package name. Multiple files can specify a package and they must all agree on what the package name is.

can contain any number of interfaces listed at the top-level and in any order
all references between interfaces must be well-formed and acyclic

can contain world definitions at the top-level in addition to interface definitions.

#### name

consists of namespace field, package field, optional version field
specified at the top of a WIT file via a package declaration

used to generate the names of imports and exports of interfaces and worlds

### Interface

collection of functions and types
unit of functionality imported from the host or implemented by a component for consumption on a host

can contain use statements, type definitions, and function definitions

All items defined in an interface, including use items, are considered as exports from the interface.
i.e. types can further be used from the interface by other interfaces

has a single namespace
i.e.none of the defined names can collide

?? can think of as instance type

### World

complete description of both imports and exports of a component
can think of as component type
better name would have been "interface"
can have multiple interfaces

describe a concrete component
are the basis of bindings generation

can contain any number of imports and exports
can be either a function or an interface

An imported or exported interface corresponds to an imported or exported instance in the component model
Functions are equivalent to bare component functions
Additionally interfaces can be defined inline with an explicit plain name that avoids the need to have an out-of-line definition

plain name of import or export statement becomes plain name of final component import or export definition

Kebab names cannot overlap and must be unique, even between imports and exports.
IDs, however, can be both imported and exported.
same interface cannot be explicitly imported or exported twice.



## Resources

- [Component Model design and specification](https://github.com/WebAssembly/component-model/tree/d1f47566f7aa9c8ab7bae2826eb9d123b2196512)
- [The `wit` format](https://github.com/WebAssembly/component-model/blob/d1f47566f7aa9c8ab7bae2826eb9d123b2196512/design/mvp/WIT.md)
