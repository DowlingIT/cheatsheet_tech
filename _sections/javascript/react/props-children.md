---
title: Props & Children
subtopic: react
group: Components & Props
order: 2
---

#### children & composition

```jsx
function Card({ title, children }) {
  return (
    <div className="card">
      <h2>{title}</h2>
      {children}
    </div>
  );
}

<Card title="Info"><p>Body content</p></Card>;
```

#### Spread props

```jsx
const props = { title: 'Info', children: 'Body' };
<Card {...props} />;
```
