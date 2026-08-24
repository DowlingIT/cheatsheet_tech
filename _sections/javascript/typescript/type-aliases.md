---
title: Type Aliases & Unions
subtopic: typescript
group: Interfaces & Type Aliases
order: 2
---

#### type alias

```ts
type ID = string | number;
type Point = { x: number; y: number };
type Callback = (err: Error | null, data?: string) => void;
```

#### Union & intersection

```ts
type Status = 'pending' | 'active' | 'done';    // literal union
type Combined = User & { createdAt: Date };       // intersection — merges shapes
```
