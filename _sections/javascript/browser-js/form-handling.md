---
title: Form Handling
subtopic: browser-js
group: Forms
order: 1
---

#### Reading & FormData

```js
form.addEventListener('submit', (e) => {
  e.preventDefault();
  const data = new FormData(form);
  data.get('email');
  Object.fromEntries(data);      // plain object built from every field
});
input.value    input.checked    select.value
```

#### Validation

```js
input.checkValidity()        // runs built-in constraints (required, pattern, etc.)
input.reportValidity()         // shows the browser's native validation UI
input.setCustomValidity('Must be a valid email')
```
