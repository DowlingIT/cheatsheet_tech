---
title: Types & typeof
subtopic: javascript-core
group: Variables & Types
order: 2
---

#### Primitive types

```js
string  number  boolean  undefined  null  symbol  bigint

typeof 'hi'        // 'string'
typeof 42           // 'number'
typeof 10n            // 'bigint'
typeof Symbol()         // 'symbol'
typeof undefined          // 'undefined'
typeof null                // 'object' — quirk, see Idioms & Gotchas
```

#### Reference types

```js
typeof {}             // 'object'
typeof []               // 'object'
typeof function () {}     // 'function'

Array.isArray([])           // true
value instanceof Array        // true — fails across iframes/realms
Object.prototype.toString.call([])  // '[object Array]' — reliable check
```
