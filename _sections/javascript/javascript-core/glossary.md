---
title: Glossary
subtopic: javascript-core
group: Terminology & Style
order: 1
---

#### Language terms

```
Hoisting     declarations moved to top of scope (var, function)
Closure      a function bundled with its captured lexical scope
Truthy/Falsy how a value coerces in a boolean context
Callback     a function passed in to be run later / on completion
```

#### Runtime terms

```
Event loop   drains the call stack, then microtasks, then macrotasks
Microtask    Promise callbacks — run before the next macrotask
Macrotask    setTimeout, setInterval, I/O — run after microtasks drain
this         set by how a function is called, not where it's defined
```
