---
title: Layouts & Templates
subtopic: nextjs
group: Layouts & Metadata
order: 1
---

#### layout vs template

```
layout.js     persists across navigations — state & DOM preserved
template.js   remounts on every navigation — fresh state, effects re-run
```

```jsx
// app/layout.js
export default function RootLayout({ children }) {
  return <html><body>{children}</body></html>;
}
```
