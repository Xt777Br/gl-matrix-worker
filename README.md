
# glMatrix for Workers
This fork are a solution for usage of glMatrix in Web Workers using the `importScripts()`

## How this work?
Simple instead of exporting as a module are created a object like the module with methods.

## Files Working:

/dist/gl-matrix.js
/dist/gl-matrix-min.js

## Usage:

#### Example of Worker:

worker.js:

```js
// importing script on creation of worker.

// Considering are at same folder
importScripts("./gl-matrix.js");

// Create object
const glm = glmatrix();

onmessage = (e) => {
    let r = glm.glMatrix.toRadian(e.data);
    postMessage(r);
}
```

## Reminders:

This is a not best to do that. But it´s very similar a module.

If you have better way you can send a pull request.

glMatrix
=======================
[![NPM Version](https://img.shields.io/npm/v/gl-matrix.svg)](https://www.npmjs.com/package/gl-matrix)
[![Build Status](https://travis-ci.org/toji/gl-matrix.svg)](https://travis-ci.org/toji/gl-matrix)

Javascript has evolved into a language capable of handling realtime 3D graphics, 
via WebGL, and computationally intensive tasks such as physics simulations.
These types of applications demand high performance vector and matrix math,
which is something that Javascript doesn't provide by default.
glMatrix to the rescue!

glMatrix is designed to perform vector and matrix operations stupidly fast! By
hand-tuning each function for maximum performance and encouraging efficient
usage patterns through API conventions, glMatrix will help you get the most out
of your browsers Javascript engine.

Learn More
----------------------
For documentation and news, visit the [glMatrix Homepage](http://glmatrix.net/)

For a tutorial, see [the "introducing glMatrix" section of _Introduction to Computer Graphics_ by David J. Eck](http://math.hws.edu/graphicsbook/c7/s1.html#webgl3d.1.2)

For a babel plugin to make writing the API nicer, see [babel-plugin-transfrom-gl-matrix](https://github.com/akira-cn/babel-plugin-transform-gl-matrix)

Regarding the current performance in modern web browsers, calling `glMatrix.setMatrixArrayType(Array)` to use normal arrays instead of Float32Arrays can greatly increase the performance.

Contributing Guidelines
----------------------
See [CONTRIBUTING.md](./CONTRIBUTING.md)

Building
----------------------
See [BUILDING.md](./BUILDING.md)
