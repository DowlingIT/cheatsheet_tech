---
title: Map & Set
subtopic: javascript-core
group: Objects & Collections
order: 3
---

#### Map

```js
const m = new Map([['a', 1]]);
m.set('b', 2);   m.get('a');   m.has('a');   m.delete('a');
m.size;
for (const [k, v] of m) { }    // iterates in insertion order
```

#### Set

```js
const s = new Set([1, 2, 2, 3]);   // dedupes automatically
s.add(4);   s.has(1);   s.delete(1);
s.size;
[...new Set(arr)];   // common idiom to dedupe an array
```
