---
title: Event Handling
subtopic: react
group: State & Events
order: 2
---

#### Handling events

```jsx
<button onClick={() => setCount(c => c + 1)}>+1</button>
<input onChange={(e) => setValue(e.target.value)} />
<form onSubmit={(e) => { e.preventDefault(); submit(); }}>
```

#### SyntheticEvent

```
onClick  onChange  onSubmit  onKeyDown  onBlur  onFocus
e.target                the DOM element that triggered the event
e.stopPropagation()   e.preventDefault()
```
