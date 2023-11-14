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



## Resources

- [Component Model design and specification](https://github.com/WebAssembly/component-model/tree/d1f47566f7aa9c8ab7bae2826eb9d123b2196512)
- [The `wit` format](https://github.com/WebAssembly/component-model/blob/d1f47566f7aa9c8ab7bae2826eb9d123b2196512/design/mvp/WIT.md)