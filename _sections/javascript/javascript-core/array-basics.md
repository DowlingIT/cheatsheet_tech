---
title: Array Basics
subtopic: javascript-core
group: Arrays
order: 1
---

#### Create & access

```js
const a = [1, 2, 3];
a.length;
a[0];                  // indexed access
a.at(-1);                // last element (negative index)
Array.from({ length: 3 }, (_, i) => i);  // [0, 1, 2]
Array.of(7);              // [7] — unlike Array(7), which makes 7 empty slots
```

#### Stack / queue / mutate

```js
a.push(v);    a.pop();
a.unshift(v);   a.shift();
a.splice(1, 2, 'x');     // remove 2 items at index 1, insert 'x'
a.slice(1, 3);              // non-mutating copy of a range
a.sort((x, y) => x - y);      // mutates — always pass a comparator for numbers
```
