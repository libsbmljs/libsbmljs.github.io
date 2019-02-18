---
title: "Getting Started"
bg: white
color: black
---

# Getting Started

Unlike most JavaScript libraries, libsbmljs is loaded asynchronously.
This means that it cannot be used immediately after importing it
because the browser may still be downloading and compiling the WebAssembly.
The libsbmljs module can be called using a `then()` method similar to a Promise:
```javascript
import libsbml from 'libsbml_stable'
// the module isn't usable yet - wait for it to load
libsbml().then((libsbml) => {
  // now it is safe to use the module
  const doc = new libsbml.SBMLDocument(3,2)
})
```
