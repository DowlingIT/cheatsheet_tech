---
title: Class Types
subtopic: typescript
group: Classes
order: 1
---

#### Access modifiers

```ts
class Account {
  public balance: number;
  private pin: string;
  protected owner: string;
  readonly id: string;

  constructor(id: string, public currency: string) {   // parameter property
    this.id = id;
  }
}
```

#### Abstract classes

```ts
abstract class Shape {
  abstract area(): number;
  describe() { return `Area: ${this.area()}`; }
}
```
