---
title: Loops
subtopic: javascript-core
group: Control Flow
order: 2
---

#### Iteration

```js
for (let i = 0; i < 10; i++) { }
for (const item of iterable) { }     // values — arrays, strings, Maps, Sets
for (const key in obj) { }            // keys — objects (avoid on arrays)
while (cond) { }
do { } while (cond);
```

#### Array-style iteration

```js
arr.forEach((item, i) => { });
for (const [i, item] of arr.entries()) { }
for (const [key, val] of Object.entries(obj)) { }
```
