---
title: Inheritance & Prototypes
subtopic: javascript-core
group: Classes & OOP
order: 2
---

#### extends & super

```js
class Dog extends Animal {
  constructor(name, breed) {
    super(name);              // must call before using `this`
    this.breed = breed;
  }
  speak() { return `${super.speak()} — woof!`; }
}
new Dog('Rex', 'Lab') instanceof Animal;  // true
```

#### Prototype chain

```js
Object.getPrototypeOf(obj);           // obj's prototype
Dog.prototype instanceof Animal;        // classes are sugar over prototypes
Object.create(protoObj);                  // create an object with an explicit prototype
```
