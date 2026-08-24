---
title: Type Narrowing
subtopic: typescript
group: Narrowing & Utility Types
order: 1
---

#### typeof / instanceof

```ts
function fmt(v: string | number) {
  if (typeof v === 'string') return v.toUpperCase();  // v is string here
  return v.toFixed(2);                                   // v is number here
}
if (err instanceof RangeError) { }
```

#### in & discriminated unions

```ts
type Shape = { kind: 'circle'; r: number } | { kind: 'square'; side: number };
function area(s: Shape) {
  if (s.kind === 'circle') return Math.PI * s.r ** 2;  // narrowed by kind
  return s.side ** 2;
}
```
