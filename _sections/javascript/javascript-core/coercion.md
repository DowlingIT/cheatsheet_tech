---
title: Type Coercion & Casting
subtopic: javascript-core
group: Variables & Types
order: 3
---

#### Explicit conversion

```js
Number('42')      Number('3.14')      Number('')     // 0
String(42)          String(null)          String(undefined)
Boolean(0)            Boolean('')            Boolean(null)  // all false
parseInt('42px')        // 42 — parses leading digits, ignores the rest
parseFloat('3.14m')       // 3.14
```

#### Implicit coercion

```js
'5' + 3        // '53' — + prefers string concatenation
'5' - 3        // 2   — -, *, / coerce operands to numbers
+'42'          // 42  — unary + converts to number
!!value        // common idiom for explicit boolean coercion
```
