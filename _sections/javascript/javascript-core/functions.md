---
title: Functions
subtopic: javascript-core
group: Functions
order: 1
---

#### Declarations

```js
function add(a, b = 0) { return a + b; }         // default param
function log(...msgs) { msgs.forEach(m => console.log(m)); }  // rest param

const double = (n) => n * 2;                       // arrow, implicit return
const greet = (name) => { return `Hi ${name}`; };     // arrow, block body
```

#### Hoisting differs by form

```js
add(1, 2);              // works — function declarations are hoisted
function add(a, b) { return a + b; }

multiply(1, 2);           // TypeError — expressions/arrows are not hoisted
const multiply = (a, b) => a * b;
```
