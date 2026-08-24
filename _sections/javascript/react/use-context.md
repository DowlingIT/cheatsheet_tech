---
title: useContext
subtopic: react
group: Performance & Context
order: 2
---

#### Context

```jsx
const ThemeContext = createContext('light');

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Toolbar />
    </ThemeContext.Provider>
  );
}

function Toolbar() {
  const theme = useContext(ThemeContext);   // reads the nearest Provider's value
}
```
