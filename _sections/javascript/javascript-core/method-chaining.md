---
title: Method Chaining
subtopic: javascript-core
group: Classes & OOP
order: 3
---

#### Chaining built-ins

```js
[1, 2, 3, 4]
  .filter(n => n % 2 === 0)
  .map(n => n * 10)
  .reduce((sum, n) => sum + n, 0);   // each step returns a value to chain off of

'  Hello World  '.trim().toLowerCase().replace(' ', '-');
```

#### Building a fluent API

```js
class QueryBuilder {
  #clauses = [];
  where(cond) { this.#clauses.push(cond); return this; }   // return this to chain
  orderBy(field) { this.#clauses.push(`ORDER BY ${field}`); return this; }
  build() { return this.#clauses.join(' '); }
}

new QueryBuilder().where('active = 1').orderBy('name').build();
```
