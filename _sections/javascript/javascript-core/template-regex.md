---
title: Template Literals & Regex
subtopic: javascript-core
group: Strings
order: 2
---

#### Template literals

```js
const name = 'Alice';
`Hello, ${name}!`;                  // interpolation
`Line one
Line two`;                            // multi-line, preserves whitespace
tag`Hello ${name}`;                     // tagged template
```

#### Regex

```js
/foo\d+/i.test(s)             // boolean match
s.match(/foo(\d+)/)             // match array, capture group in [1]
s.matchAll(/\d+/g)                // iterator of all matches
s.replace(/\s+/g, ' ')              // regex-based replace
```
