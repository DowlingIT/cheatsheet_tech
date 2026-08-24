---
title: Declarations
subtopic: javascript-core
group: Variables & Types
order: 1
---

#### let, const, var

```js
let x = 1;         // block-scoped, reassignable
const y = 2;         // block-scoped, binding cannot be reassigned
var z = 3;             // function-scoped, hoisted — avoid in modern code

const arr = [1, 2];
arr.push(3);            // OK — const locks the binding, not the contents
```

#### Hoisting & TDZ

```js
console.log(a);   // undefined — var is hoisted, initialized to undefined
var a = 1;

console.log(b);   // ReferenceError — temporal dead zone
let b = 1;
```
