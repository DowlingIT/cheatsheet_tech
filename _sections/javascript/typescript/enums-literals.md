---
title: Enums & Literal Types
subtopic: typescript
group: Enums & Literals
order: 1
---

#### Enums

```ts
enum Status { Pending, Active, Done }        // numeric — 0, 1, 2
Status.Active                                   // 1

enum Direction { Up = 'UP', Down = 'DOWN' }       // string enum — more debuggable
```

#### Literal types & as const

```ts
type Level = 'low' | 'medium' | 'high';
let level: Level = 'medium';

const config = { mode: 'dark' } as const;   // literal, deeply readonly
```
