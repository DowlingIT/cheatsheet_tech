---
title: useRef
subtopic: react
group: Effects & Refs
order: 2
---

#### useRef

```jsx
const inputRef = useRef(null);
useEffect(() => { inputRef.current.focus(); }, []);
<input ref={inputRef} />;

const renderCount = useRef(0);
renderCount.current++;   // mutable value that persists without triggering a re-render
```
