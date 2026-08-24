---
title: Utility Types
subtopic: typescript
group: Narrowing & Utility Types
order: 2
---

#### Common utility types

```ts
Partial<User>              // all properties optional
Required<User>               // all properties required
Readonly<User>                 // all properties readonly
Pick<User, 'id' | 'name'>        // subset of keys
Omit<User, 'email'>                // all keys except these
Record<string, User>                 // object keyed by string
```

#### More utilities

```ts
ReturnType<typeof fn>        // infer a function's return type
Parameters<typeof fn>          // tuple of a function's parameter types
NonNullable<string | null>       // strips null/undefined → string
```
