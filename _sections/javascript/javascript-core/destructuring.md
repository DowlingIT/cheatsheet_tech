---
title: Destructuring & Spread
subtopic: javascript-core
group: Operators
order: 2
---

#### Destructuring

```js
const [first, second, ...rest] = [1, 2, 3, 4];
const { id, name: userName, ...others } = user;
const { a = 1, b = 2 } = options;          // defaults
function greet({ name, age = 0 }) {}        // in parameters
```

#### Spread & rest

```js
const merged = { ...defaults, ...overrides };   // later keys win
const combined = [...arr1, ...arr2];
function sum(...nums) { return nums.reduce((a, b) => a + b, 0); }
Math.max(...[1, 5, 3]);
```
