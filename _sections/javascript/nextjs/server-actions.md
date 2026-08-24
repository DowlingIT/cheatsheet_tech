---
title: Server Actions
subtopic: nextjs
group: Server Actions & API
order: 1
---

#### Defining & using

```jsx
'use server';
async function createPost(formData) {
  await db.posts.create({ title: formData.get('title') });
  revalidatePath('/posts');
}

// in a Server Component
<form action={createPost}>
  <input name="title" />
  <button type="submit">Create</button>
</form>
```
