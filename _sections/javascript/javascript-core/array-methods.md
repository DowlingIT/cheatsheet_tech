---
title: Array Methods
subtopic: javascript-core
group: Arrays
order: 2
---

#### Transform

```
arr.map(x => x * 2)
arr.filter(x => x > 0)
arr.reduce((a, b) => a + b, 0)
arr.flat()   arr.flatMap(x => [x, x])
```

#### Search

```
arr.find(x => x.id === 1)
arr.findIndex(x => x.id === 1)
arr.includes(value)
arr.indexOf(value)
arr.some(x => x > 10)
arr.every(x => x > 0)
```

#### Iterate

```
arr.forEach(x => console.log(x))
```
