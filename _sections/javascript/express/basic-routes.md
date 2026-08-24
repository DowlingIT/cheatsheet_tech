---
title: Basic Routes
subtopic: express
group: Routing
order: 1
---

#### HTTP methods & params

```js
app.get('/users', (req, res) => res.json(users));
app.post('/users', (req, res) => res.status(201).json(newUser));
app.put('/users/:id', (req, res) => {});
app.delete('/users/:id', (req, res) => {});

app.get('/users/:id', (req, res) => {
  const { id } = req.params;      // route param
  res.json({ id });
});
```
