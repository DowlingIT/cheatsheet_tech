---
title: Error Handling
subtopic: javascript-core
group: Error Handling
order: 1
---

#### try/catch/finally

```js
try {
  risky();
} catch (err) {
  console.error(err.message);
} finally {
  cleanup();      // always runs
}
```

#### Custom errors

```js
class ValidationError extends Error {
  constructor(message, field) {
    super(message);
    this.name = 'ValidationError';
    this.field = field;
  }
}
throw new ValidationError('Required', 'email');
err instanceof Error   // true — custom errors still match the base class
```
