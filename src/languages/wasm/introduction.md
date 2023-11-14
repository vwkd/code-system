# WebAssembly (Wasm)



## Introduction

- binary instruction format for a stack-based virtual machine
- portable compilation target for programming languages
- memory-safe sandboxed execution environment

executes at native speed on a wide range of platforms

stack machine
is encoded in a size- and load-time-efficient binary format

- safe, portable, low-level code format
- for efficient execution and compact representation


semantics
Fast, safe, and portable
Fast: executes with near native code performance, taking advantage of capabilities common to all contemporary hardware.
Safe: code is validated and executes in a memory-safe, sandboxed environment preventing data corruption or security breaches.
Well-defined: fully and precisely defines valid programs and their behavior in a way that is easy to reason about informally and formally.
Hardware-independent: can be compiled on all modern architectures, desktop or mobile devices and embedded systems alike.
Language-independent: does not privilege any particular language, programming model, or object model.
Platform-independent: can be embedded in browsers, run as a stand-alone VM, or integrated in other environments.
Open: programs can interoperate with their environment in a simple and universal manner.

representation
Efficient and portable
Compact: has a binary format that is fast to transmit by being smaller than typical text or native code formats.
Modular: programs can be split up in smaller parts that can be transmitted, cached, and consumed separately.
Efficient: can be decoded, validated, and compiled in a fast single pass, equally with either just-in-time (JIT) or ahead-of-time (AOT) compilation.
Streamable: allows decoding, validation, and compilation to begin as soon as possible, before all data has been seen.
Parallelizable: allows decoding, validation, and compilation to be split into many independent parallel tasks.
Portable: makes no architectural assumptions that are not broadly supported across modern hardware.

code is also easy to inspect and debug

- virtual instruction set architecture (ISA)
- encodes a low-level, assembly-like programming language


- low-level virtual machine
- language-independent, platform-independent
- portable, deterministic, sandboxed
- open standard

modules
have explicit imports and exports

- beware: misnomer, not only for Web, historical origins ❗️


- universal execution environment




### instruction set
### binary encoding
### validation
### execution semantics
### textual representation

### Textual format

- for debugging, testing, experimenting, optimizing, learning, teaching, and writing programs by hand

- versionless, feature-tested, and backwards-compatible

modules



## Resources

- [](https://webassembly.org/)
- [Andreas Rossberg - As low-level as possible, but not lower](https://youtube.com/live/bjJU1vP1vVI?feature=shared&t=17238)
