---
title: Idioms & Gotchas
subtopic: javascript-core
group: Terminology & Style
order: 2
---

#### Equality & NaN

```js
0 == '0'            // true  — loose, coerces types
0 === '0'            // false — strict, no coercion (prefer this)
NaN === NaN           // false — NaN never equals itself
Number.isNaN(NaN)      // true — use this, not the global isNaN()
0.1 + 0.2               // 0.30000000000000004 — float precision
```

#### var vs let/const

```js
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 0);   // 3, 3, 3 — var is function-scoped
}
for (let i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 0);   // 0, 1, 2 — let is block-scoped
}
```

#### Sneaky quirks

```js
typeof null              // 'object' — long-standing bug, kept for compat
[1, , 3].length            // 3 — sparse array, the hole isn't undefined
Array.isArray([])            // true — typeof [] is only ever 'object'
[] + []                        // '' — both coerce to strings and concat
```
