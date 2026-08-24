---
title: Arrays, Tuples & Objects
subtopic: typescript
group: Types
order: 2
---

#### Arrays & tuples

```ts
let tags: string[];
let tags2: Array<string>;
let pair: [string, number];              // tuple — fixed length & types
let row: [number, ...string[]];            // tuple with a rest element
```

#### Object shapes

```ts
let user: { id: number; name: string; active?: boolean };
let dict: { [key: string]: number };         // index signature
let dict2: Record<string, number>;             // equivalent, and preferred
```
