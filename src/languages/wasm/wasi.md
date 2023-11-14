# WebAssembly System Interface (WASI)



## Introduction

modular system interface to run WebAssembly

set of APIs
modular collection of APIs
- beware: misnomer, not necessarily system, historical origins ❗️

- better name would be WebAssembly Standard Interfaces

set of portable, modular, runtime-independent, and WebAssembly-native APIs to interact with the outside world
Capability-based API design to preserve the essential sandboxed nature of WebAssembly
designed with capability-based security principles, using the facilities provided by the Wasm component model
All access to external resources is provided by capabilities.

no ambient authorities, i.e. no global namespaces at runtime, and no global functions at link time

## capabilities

beware: differentthan Linux capabilities or the withdrawn POSIX capabilities, which are per-process rather than per-resource

### Handles

defined in the component-model type system
dynamically identify and provide access to resources.
unforgeable, meaning there's no way for an instance to acquire access to a handle other than to have another instance explicitly pass one to it

### Link-time capabilities
functions which require no handle arguments
used sparingly, in situations where it's not necessary to identify more than one instance of a resource at runtime
interposable, so they are still refusable in a capability-based security sense



Interposition
ability for a Webassembly instance to implement a given WASI interface, and for a consumer WebAssembly instance to be able to use this implementation transparently
This can be used to adapt or attenuate the functionality of a WASI API without changing the code using it
interfaces always support link-time interposition
While WASI APIs are often implemented in hosts, they can also be implemented in Wasm, which may itself be a wrapper around the host
This may be used to implement attenuation, providing filtered access to the underlying host-provided functionality.

- beware: also called "virtualization"

worlds
allows specific sets of APIs to be described which meet the needs of different environments.
engines don't need to implement every API


layered on top of the Component Model


like OS's many I/O interfaces



## Resources

- [WebAssembly System Interface](https://github.com/WebAssembly/WASI/tree/2980bb39e1d2a4a2adae4748908cb4325cd41a26)
- [WASI - The WebAssembly System Interface](https://wasi.dev)
- [WASI Document Guide](https://github.com/bytecodealliance/wasmtime/blob/321294a5d21f7006a959ba378ebd32782a76d3d2/docs/WASI-documents.md)
