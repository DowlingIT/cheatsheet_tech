---
title: useMemo & useCallback
subtopic: react
group: Performance & Context
order: 1
---

#### Memoization

```jsx
const sorted = useMemo(() => [...items].sort(cmp), [items]);   // memoize a value

const handleClick = useCallback(() => {
  doSomething(id);
}, [id]);                                                          // memoize a function

const Memoized = React.memo(Component);    // skip re-render if props are shallow-equal
```
