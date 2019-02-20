---
title: "Tutorial"
bg: white
color: black
---

# Tutorial

This tutorial will teach you the basics of using libsbmljs in an empty project.
Make sure you have Node.js 10.15.0 or later before starting.
We're going to use Node.js for this tutorial because setting up libsbmljs in the browser usually involves Webpack, which makes things a little more complicated. We have a separate [example](https://github.com/libsbmljs/examples) showing how to use libsbmljs with Webpack.

1. First, create and change to a new directory and run:

```
npm init
```

The answers you provide to npm's questions don't matter for this tutorial. You can leave all of the fields blank.

2. You will need to install one of libsbmljs's npm packages. We will use the `libsbmljs_stable` package for this tutorial.

```
npm install --save libsbmljs_stable@beta
```

3. Next you will need to install Babel:

```
npm install --save-dev @babel/core @babel/cli @babel/preset-env
```

4. Create the file `index.js` in the current directory. This file will hold all the JavaScript code for this tutorial.

5. Open the `main.js` file. Unlike most JavaScript libraries, libsbmljs is loaded asynchronously.
This means that it cannot be used immediately after importing it
because the browser or Node.js may still be downloading and compiling it.
The libsbmljs module can be called using a `then()` method similar to a [Promise](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise). Any libsbmljs methods you want to use should go inside the `then()` callback. Add the following code to your `main.js` file:
```javascript
import libsbml from 'libsbmljs_stable'
// the module isn't usable yet - wait for it to load
libsbml().then((libsbml) => {
  // now it is safe to use the module
  const doc = new libsbml.SBMLDocument(3,2)
})
```

6. To populate the SBML content to the document you just created in the previous step, let's add one SBML Comaprtment, Species and one Reaction. You can paste this code into your `then()` callback or copy the full source code at the end of this tutorial into `index.js`.

```javascript
...
  // create a model and compartment
  const model = doc.createModel()
  const compartment = model.createCompartment()
  compartment.setId('C1')
  compartment.setSize(1)
  compartment.setConstant(true)

  // create a species
  const species = model.createSpecies()
  species.setId('S1')
  species.setConstant(false)
  species.setHasOnlySubstanceUnits(false)
  species.setBoundaryCondition(false)

  // create a reaction
  const reaction = model.createReaction()
  reaction.setId('J1')
  reaction.setReversible(false)

  // create a parser for infix formulae
  // this is a helper class of libsbmljs
  // it doesn't exist in the libsbml C++ library
  const parser = new libsbml.SBMLFormulaParser()
  reaction.createKineticLaw().setMath(parser.parseL3Formula('10*S1'))
...
```
