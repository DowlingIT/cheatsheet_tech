---
title: Metadata & SEO
subtopic: nextjs
group: Layouts & Metadata
order: 2
---

#### Static & dynamic metadata

```js
export const metadata = {
  title: 'My Site',
  description: 'A great site',
};

export async function generateMetadata({ params }) {
  const post = await getPost(params.id);
  return { title: post.title };
}
```
