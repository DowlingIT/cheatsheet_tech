---
title: useState
subtopic: react
group: State & Events
order: 1
---

#### useState

```jsx
const [count, setCount] = useState(0);

setCount(count + 1);              // may read a stale count within the same tick
setCount(prev => prev + 1);         // functional update — always safe to chain

const [user, setUser] = useState({ name: '', age: 0 });
setUser(prev => ({ ...prev, name: 'Alice' }));   // merge manually — no auto-merge
```
