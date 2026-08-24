---
title: Object Methods
subtopic: javascript-core
group: Objects & Collections
order: 2
---

#### Static Object methods

```js
Object.keys(o)          // ['id', 'name']
Object.values(o)          // [1, 'Alice']
Object.entries(o)           // [['id', 1], ['name', 'Alice']]
Object.assign({}, a, b)       // shallow merge, mutates the first arg
Object.freeze(o)   Object.isFrozen(o)
Object.fromEntries([['a', 1]])  // { a: 1 }
```

#### Merge & clone

```js
const merged = { ...a, ...b };         // shallow merge, later keys win
const clone = { ...o };                  // shallow clone
const deepClone = structuredClone(o);      // deep clone (modern runtimes)
```
