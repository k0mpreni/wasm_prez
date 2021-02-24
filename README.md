---
marp: true
---
<!-- theme: uncover -->
<!-- size: a4 -->

# WebAssembly
---
## What is WASM

WebAssembly is a low level assembly-like language which provides a compilation target for languages so that they can run on the web.
It's an open standard inside the W3C WebAssembly Community Group.

---

## Goals
- Fast, efficient and portable => take advantage of common hardware capabilities
- Readable and debuggable => have a human-readable text format
- Secure => run in a sandbox and enforce the browser's same-origin and permissions  policies
- Don't break the web => Designed to work with other web technologies and maintains backwards compatibility

---

## Why WASM

Slow performances when using JavaScript with 3D Games, VR VA, computer vision, image editing...

High cost of download parsing and compiling very large JS applications (can be a problem with slow internet connections and not high performant devices)

---

## Integration with the web platfom

---

### How does it work?

---

The web plaform:
A VM runs the web app's code (the JS code that powers the app)

A set of __Web APIs__ (DOM CSSDOM WebGl, IndexedDB...)

---

The WASM code is execute in a new VM alongside with the JS VM. This VM export WASM code wrapped by the WebAssembly Javascript API so we will Javascript functions to call in our application.

JS has complete over how WASM code is dowloaded, compiled and run; it's like a JS feature for eefficiently generating high performance functions.

The **WebAssembly module** can also import and synchronously call Javascript functions.

---

## Key concepts

---

- __Module__: A stateless binary, declares imports and exports

---
- __Memory__: A resizable ArrayBuffer where you can write and read with WASM low-level memory access instructions and is shared between WASM and JS
---
- __Table__: A resizable typed array of references (for the moment only to functions) that is accessible and mutable from JS and WASM (for safety and portability reasons)
---
- __Instance__: A Module paired with all the state it uses at runtime including a Memory, Table, and set of imported values. An Instance is like an ES2015 module that has been loaded into a particular global with a particular set of imports.

---
### Available languages
---
16 stable languages suitable for a production usage:
    - .Net 
    - C#
    - C
    - C++
    - Go
    - Rust
    - AssemblyScript
    - ...

---

20 unstable but usable
    - PHP
    - Python
    - Javascript
    - Ruby
    - Java
    - Kotlin/Native
    - ...

---

11 WIP
    - Ocaml
    - Haskell
    - ...

---

## Demo time

https://github.com/mdn/webassembly-examples/blob/master/js-api-examples/simple.wat

https://github.com/imalexlab/Pretty-JSON

https://alexlab.me/random
https://github.com/imalexlab/alexlab/tree/master/src/routes/experiments

---

## Performances

Javascript may be faster for little arrays.
WebAssembly faster on heavy calculation.
Native is faster than JS

---

## Cons
    - Can be complex to get in
    - Not a lot of documentation
    - If need to emulate a native behavior, it can lead to poor performances.
    - New ways to create security flaws (Browser exploits, keyloggers)

---

## Future
- Direct call of WebAPIs from the wasm module
- Loaded like ES2015 modules (using <script type='module'>)
- WebAssembly as a real platform (backend, IOT)

---

## Links
https://github.com/appcypher/awesome-wasm-langs
https://developer.mozilla.org/en-US/docs/WebAssembly
https://webassembly.org/
https://webassembly.studio/
https://github.com/mdn/webassembly-examples/tree/master/js-api-examples
https://medium.com/@torch2424/webassembly-is-fast-a-real-world-benchmark-of-webassembly-vs-es6-d85a23f8e193
https://www.usenix.org/system/files/atc19-jangda.pdf
