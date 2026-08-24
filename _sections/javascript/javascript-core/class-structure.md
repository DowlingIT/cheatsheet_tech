---
title: Class Structure
subtopic: javascript-core
group: Classes & OOP
order: 1
---

#### Class anatomy

```js
class Animal {
  #age = 0;                 // private field
  static count = 0;

  constructor(name) {
    this.name = name;
    Animal.count++;
  }

  speak() { return `${this.name} makes a sound`; }
  static create(name) { return new Animal(name); }

  get age() { return this.#age; }
  set age(value) { this.#age = value; }
}
```

#### Field & method kinds

```
public field       name = 'x'
private field       #name = 'x'    only accessible inside the class body
static member         static count = 0
static private          static #count = 0
getter/setter              get x() {}  /  set x(v) {}
```
