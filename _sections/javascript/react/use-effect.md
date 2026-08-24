---
title: useEffect
subtopic: react
group: Effects & Refs
order: 1
---

#### useEffect

```jsx
useEffect(() => {
  const id = setInterval(tick, 1000);
  return () => clearInterval(id);     // cleanup — runs before the next effect / unmount
}, []);                                 // deps: [] = once, omitted = every render

useEffect(() => { document.title = `${count} clicks`; }, [count]);
```
