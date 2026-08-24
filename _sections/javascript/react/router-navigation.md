---
title: Navigation & Params
subtopic: react
group: React Router
order: 2
---

#### Navigating & reading params

```jsx
import { Link, useNavigate, useParams, useSearchParams } from 'react-router-dom';

<Link to="/posts/1">View post</Link>;
const navigate = useNavigate();
navigate('/posts/1');

const { id } = useParams();               // from /posts/:id
const [params] = useSearchParams();         // ?sort=asc
params.get('sort');
```
