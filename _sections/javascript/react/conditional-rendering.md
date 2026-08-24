---
title: Conditional Rendering
subtopic: react
group: Lists, Conditionals & Forms
order: 2
---

#### Patterns

```jsx
{isLoggedIn ? <Dashboard /> : <Login />}
{error && <ErrorBanner message={error} />}

function Status({ status }) {
  if (status === 'loading') return <Spinner />;
  if (status === 'error') return <ErrorBanner />;
  return <Content />;
}
```
