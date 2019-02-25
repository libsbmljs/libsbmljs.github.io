---
title: "Installation"
bg: blue2
color: white
---

# Installation

Choose one of the following packages:

* No SBML extensions (i.e. cannot read flux-balance models) but smallest size
```
npm install --save libsbmljs_core@beta
```

* Everything from the previous package plus accepted SBML extensions (CAN read flux-balance models)
```
npm install --save libsbmljs_stable@beta
```

* Everything from the previous package plus all SBML extensions (including proposed extensions)
```
npm install --save libsbmljs_experimental@beta
```

These packages get larger but have more features as you go down the list.
Your choice will depend on which SBML extensions you need, and how much
bandwidth you want to conserve.
If you are unsure, go with `libsbmljs_stable`.
If you would like more info, keep reading.

<br/>
<br/>
<br/>

## Why Three NPM Packages?

libsbmljs comes in [libsbmljs_core](https://www.npmjs.com/package/libsbmljs_core), [libsbmljs_stable](https://www.npmjs.com/package/libsbmljs_stable), and [libsbmljs_experimental](https://www.npmjs.com/package/libsbmljs_experimental) npm packages.
The difference between them is the number of [SBML extensions](http://sbml.org/Documents/Specifications#SBML_Level_3_Packages) supported in each version.
If you don't know what extensions you need, go with the "stable" package.
It can read all models in the [BioModels](http://www.ebi.ac.uk/biomodels/) and [BiGG Models](http://bigg.ucsd.edu/) databases.

<center/>
|`core`|`stable`|`experimental`|
|---|---|---|
| (no extensions) | [layout](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/layout) | [layout](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/layout) |
|   |[render](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/render)|[render](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/render)|
|   |[fbc](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/fbc) |[fbc](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/fbc)|
|   |[multi](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/multi) |[multi](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/multi)|
|   |[qual](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/qual) |[qual](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/qual)|
|   |[comp](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/comp) |[comp](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/comp)|
|   |[groups](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/groups) |[groups](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/groups)|
|   ||[distrib](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/distrib)|
|   ||[dyn](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/dyn)|
|   ||[arrays](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/arrays)|
|   ||[spatial](http://sbml.org/Documents/Specifications/SBML_Level_3/Packages/spatial)|

The libSBML C++ library maintains two separate branches:
the "stable" branch for accepted extensions
and the "experimental" branch for proposed extensions.
The extensions in the experimental branch are not finalized yet - they are subject to change,
and any code that relies on them will have to be changed as well.
If you don't require any SBML extensions at all, you can go with the "core" build, which has the added benefit of giving you the smallest npm package.

Package size (uncompressed):

|`core`|3.0M|
|`stable`|6.4M|
|`experimental`|9.5M|
