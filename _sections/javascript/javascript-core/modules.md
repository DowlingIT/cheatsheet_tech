---
title: Modules
subtopic: javascript-core
group: Modules & Packages
order: 1
---

#### ES modules

```js
export const PI = 3.14;
export default function main() { }
export { helperA, helperB };

import main, { PI, helperA as alias } from './module.js';
import * as utils from './utils.js';
```

#### CommonJS (Node)

```js
module.exports = { add, subtract };
exports.add = (a, b) => a + b;

const { add } = require('./math');
const path = require('path');
```
