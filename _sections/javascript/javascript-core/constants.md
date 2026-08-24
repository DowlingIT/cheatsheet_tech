---
title: Constants
subtopic: javascript-core
group: Variables & Types
order: 4
---

#### const & immutability

```js
const MAX_RETRIES = 3;              // convention: UPPER_CASE for true constants
const config = Object.freeze({ debug: false });  // shallow immutability
config.debug = true;                  // silently ignored (throws in strict mode)
```

#### Useful built-in constants

```js
Number.MAX_SAFE_INTEGER    Number.MIN_SAFE_INTEGER
Number.EPSILON               Number.POSITIVE_INFINITY
Math.PI    Math.E
undefined  null  NaN  Infinity
```
