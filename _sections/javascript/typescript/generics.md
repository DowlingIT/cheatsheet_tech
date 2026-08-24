---
title: Generics
subtopic: typescript
group: Functions & Generics
order: 2
---

#### Generic functions & types

```ts
function first<T>(arr: T[]): T | undefined { return arr[0]; }
first<number>([1, 2, 3]);         // explicit type argument
first(['a', 'b']);                  // inferred as string

interface Box<T> { value: T; }
const box: Box<string> = { value: 'hi' };
```

#### Constraints & defaults

```ts
function longest<T extends { length: number }>(a: T, b: T): T {
  return a.length >= b.length ? a : b;
}
interface Container<T = string> { value: T; }
```
