---
title: Function Types
subtopic: typescript
group: Functions & Generics
order: 1
---

#### Typed functions

```ts
function add(a: number, b: number): number { return a + b; }
const mul = (a: number, b: number): number => a * b;

type Adder = (a: number, b: number) => number;
function apply(fn: Adder, a: number, b: number) { return fn(a, b); }
```

#### Optional, default & rest

```ts
function greet(name: string, greeting = 'Hi'): string { return `${greeting}, ${name}`; }
function log(...msgs: string[]): void {}
function find(id?: number): User | undefined {}
```
