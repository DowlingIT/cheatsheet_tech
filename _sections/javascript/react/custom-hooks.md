---
title: Custom Hooks
subtopic: react
group: Reducer & Custom Hooks
order: 2
---

#### Custom hooks

```jsx
function useToggle(initial = false) {
  const [value, setValue] = useState(initial);
  const toggle = useCallback(() => setValue(v => !v), []);
  return [value, toggle];      // convention: hook names start with `use`
}

const [isOpen, toggleOpen] = useToggle();
```
