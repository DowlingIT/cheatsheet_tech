---
title: Controlled Forms
subtopic: react
group: Lists, Conditionals & Forms
order: 3
---

#### Controlled inputs

```jsx
const [value, setValue] = useState('');

<input value={value} onChange={(e) => setValue(e.target.value)} />
<textarea value={text} onChange={(e) => setText(e.target.value)} />
<select value={choice} onChange={(e) => setChoice(e.target.value)}>
  <option value="a">A</option>
</select>
```
