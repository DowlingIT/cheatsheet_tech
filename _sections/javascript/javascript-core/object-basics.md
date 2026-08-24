---
title: Object Basics
subtopic: javascript-core
group: Objects & Collections
order: 1
---

#### Create & access

```js
const o = { id: 1, name: 'Alice' };
o.name;                    // dot access
o['name'];                   // bracket access — needed for dynamic keys
o.newProp = 'val';             // add
delete o.newProp;                // remove
'name' in o;                       // key check, includes inherited
o.hasOwnProperty('name');            // own property only
```

#### Optional chaining

```js
o?.address?.city;        // undefined if any link is nullish
o?.method?.();             // safe call
o?.[dynamicKey];             // safe dynamic access
```
