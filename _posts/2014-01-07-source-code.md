---
title: "Source Code"
bg: white
color: black
---

# Source Code

The source code of the libsbmljs wrapper *per se* is actually a set of build scripts and WebIDL interface files which can be used to generate a WebAssembly / JavaScript wrapper from a given checkout of the libSBML C++ source code. The libsbmljs wrapper uses [Emscripten](https://emscripten.org/index.html) to build WebAssembly / JavaScript bindings.

The build scripts generating the libsbmljs wrapper along with instructions for using them are available at [GitHub](https://github.com/libsbmljs/libsbmljs).

If you're looking for the source code of libSBML itself, please visit the [libSBML site](http://sbml.org/Software/libSBML).
