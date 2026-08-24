---
title: Testing
subtopic: django
group: Testing & CLI
order: 1
---

#### TestCase & Client

```python
from django.test import TestCase, Client
from django.urls import reverse
from .models import Post

class PostTests(TestCase):
    @classmethod
    def setUpTestData(cls):          # runs once for the class
        cls.user = User.objects.create_user(
            username='alice', password='secret')
        cls.post = Post.objects.create(
            title='Hello', author=cls.user, status='published')

    def test_post_list_status(self):
        response = self.client.get(reverse('post-list'))
        self.assertEqual(response.status_code, 200)

    def test_post_list_context(self):
        response = self.client.get(reverse('post-list'))
        self.assertContains(response, 'Hello')
        self.assertIn('posts', response.context)

    def test_post_create_requires_auth(self):
        response = self.client.post(reverse('post-create'), data={})
        self.assertRedirects(response, '/login/?next=/posts/new/')

    def test_post_create_authenticated(self):
        self.client.login(username='alice', password='secret')
        response = self.client.post(reverse('post-create'),
            data={'title': 'New', 'body': 'Content', 'status': 'draft'})
        self.assertEqual(Post.objects.count(), 2)
```
