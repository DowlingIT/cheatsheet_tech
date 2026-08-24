---
title: util
subtopic: nodejs
group: Utilities
order: 1
---

#### util

```js
const { promisify, inspect } = require('util');
const readFileAsync = promisify(fs.readFile);   // convert a callback API to promises

util.inspect(obj, { depth: null, colors: true });
util.format('%s is %d', 'age', 30);
```
