---
title: JSON
subtopic: javascript-core
group: Built-ins
order: 3
---

#### Parse & stringify

```js
JSON.stringify({ a: 1 })              // '{"a":1}'
JSON.stringify(obj, null, 2)            // pretty-printed, 2-space indent
JSON.parse('{"a":1}')                     // { a: 1 }
JSON.parse(str, (key, val) => val)          // reviver function, per key
```
