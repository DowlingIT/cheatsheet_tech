---
title: useReducer
subtopic: react
group: Reducer & Custom Hooks
order: 1
---

#### useReducer

```jsx
function reducer(state, action) {
  switch (action.type) {
    case 'increment': return { count: state.count + 1 };
    case 'reset':      return { count: 0 };
    default:            throw new Error(`Unknown action: ${action.type}`);
  }
}

const [state, dispatch] = useReducer(reducer, { count: 0 });
dispatch({ type: 'increment' });
```
