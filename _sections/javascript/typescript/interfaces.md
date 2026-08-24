---
title: Interfaces
subtopic: typescript
group: Interfaces & Type Aliases
order: 1
---

#### Interface

```ts
interface User {
  readonly id: number;
  name: string;
  email?: string;              // optional
  greet(): string;
}

interface Admin extends User {
  role: 'admin' | 'owner';
}
```

#### Implementing

```ts
class Employee implements User {
  constructor(public id: number, public name: string) {}
  greet() { return `Hi, ${this.name}`; }
}
```
