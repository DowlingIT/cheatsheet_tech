---
title: Function Components
subtopic: react
group: Components & Props
order: 1
---

#### Function component

```jsx
function Greeting({ name, age = 0 }) {
  return <h1>Hello, {name}! You are {age}.</h1>;
}

<Greeting name="Alice" age={30} />;
```

#### Fragments

```jsx
function List() {
  return (
    <>
      <li>One</li>
      <li>Two</li>
    </>
  );   // fragment — groups elements without adding a DOM node
}
```
