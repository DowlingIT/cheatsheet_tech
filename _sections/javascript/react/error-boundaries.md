---
title: Error Boundaries
subtopic: react
group: Patterns
order: 2
---

#### Error boundary (class component — no hook equivalent)

```jsx
class ErrorBoundary extends React.Component {
  state = { hasError: false };
  static getDerivedStateFromError() { return { hasError: true }; }
  componentDidCatch(error, info) { logError(error, info); }
  render() {
    return this.state.hasError ? <Fallback /> : this.props.children;
  }
}
```
