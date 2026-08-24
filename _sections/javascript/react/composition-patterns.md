---
title: Composition Patterns
subtopic: react
group: Patterns
order: 1
---

#### Render props & compound components

```jsx
function DataProvider({ render }) {
  const data = useData();
  return render(data);            // render prop — caller controls what renders
}

<Tabs>                            {/* compound component — shares state via context */}
  <Tabs.List><Tabs.Tab>One</Tabs.Tab></Tabs.List>
  <Tabs.Panels><Tabs.Panel>Content</Tabs.Panel></Tabs.Panels>
</Tabs>
```
