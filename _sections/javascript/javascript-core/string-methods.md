---
title: String Methods
subtopic: javascript-core
group: Strings
order: 1
---

#### Search & test

```js
s.includes('foo')
s.startsWith('foo')
s.endsWith('foo')
s.indexOf('foo')     // -1 if not found
s.length
```

#### Transform

```js
s.toUpperCase()   s.toLowerCase()
s.trim()   s.trimStart()   s.trimEnd()
s.replace('a', 'b')          // first match only
s.replaceAll('a', 'b')
s.padStart(5, '0')   s.padEnd(5, '0')
s.split(',')   s.slice(2, 5)
```
