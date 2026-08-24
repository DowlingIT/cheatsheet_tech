---
title: Lists & Keys
subtopic: react
group: Lists, Conditionals & Forms
order: 1
---

#### Rendering lists

```jsx
{items.map(item => (
  <li key={item.id}>{item.name}</li>     // key must be stable & unique among siblings
))}

{items.length === 0 && <p>No items</p>}
```
