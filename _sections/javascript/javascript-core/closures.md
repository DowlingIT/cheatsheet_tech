---
title: Closures & this
subtopic: javascript-core
group: Functions
order: 2
---

#### Closures

```js
function makeCounter() {
  let count = 0;
  return () => ++count;   // closes over count
}
const counter = makeCounter();
counter();   // 1
counter();   // 2
```

#### this binding

```js
const obj = {
  name: 'A',
  regular() { return this.name; },   // this === obj when called as obj.regular()
  arrow: () => this.name,              // this === enclosing scope, not obj
};

fn.call(obj, arg1);           // invoke with this = obj
fn.apply(obj, [arg1]);          // same, args passed as an array
const bound = fn.bind(obj);       // new function with this permanently locked
```
