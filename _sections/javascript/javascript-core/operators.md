---
title: Operators
subtopic: javascript-core
group: Operators
order: 1
---

#### Comparison & logical

```js
==   // loose equality — coerces types
===  // strict equality — no coercion (prefer this)
&&   ||   !                  // logical
??                             // nullish coalescing — null/undefined only
a ?? 'default'                   // vs a || 'default' (also catches 0, '', false)
```

#### Optional chaining & logical assignment

```js
user?.address?.city         // undefined if any link is null/undefined
user?.getName?.()             // safe method call

a ??= 'default'                 // assign only if a is null/undefined
a ||= fallback                    // assign only if a is falsy
a &&= transform(a)                  // assign only if a is truthy
```
