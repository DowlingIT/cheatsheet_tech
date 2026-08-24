---
title: Date & Time
subtopic: javascript-core
group: Built-ins
order: 2
---

#### Create & read

```js
new Date()                    // now
new Date('2026-01-01')
new Date(2026, 0, 1)             // year, month (0-indexed!), day
Date.now()                          // ms since epoch, as a number

d.getFullYear()  d.getMonth()  d.getDate()  d.getDay()
d.getHours()  d.getTime()
```

#### Format & manipulate

```js
d.toISOString()               // '2026-01-01T00:00:00.000Z'
d.toLocaleDateString()          // locale-formatted
d.setDate(d.getDate() + 7);       // mutates in place — Date has no immutable API
new Date(d.getTime() + 86400000);   // add a day without mutating
```
