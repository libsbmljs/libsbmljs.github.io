---
title: "Tutorial"
bg: white
color: black
---

# Tutorial

This tutorial will teach you the basics of using libsbmljs in an empty project. Make sure you have Node.js 10.15.0 or later before starting.
We're going to use Node.js for this tutorial because setting up libsbmljs in the browser usually involves Webpack, which makes things a little more complicated. We have a separate [example](https://github.com/libsbmljs/examples) showing how to use libsbmljs with Webpack.

1. First, create and change to a new directory and run:

```
npm init
```

The answers you provide to npm's questions don't matter for this tutorial. You can leave all of the fields blank.

2. You will need to install one of libsbmljs's npm packages. We will use

```
npm install --save libsbmljs_stable@beta
```

3. We will need Babel to run the example. Install it with:

```
npm install --save-dev @babel/core @babel/cli @babel/preset-env
```

Unlike most JavaScript libraries, libsbmljs is loaded asynchronously.
This means that it cannot be used immediately after importing it
because the browser may still be downloading and compiling it.
The libsbmljs module can be called using a `then()` method similar to a Promise:
```javascript
import libsbml from 'libsbml_stable'
// the module isn't usable yet - wait for it to load
libsbml().then((libsbml) => {
  // now it is safe to use the module
  const doc = new libsbml.SBMLDocument(3,2)
})
```
