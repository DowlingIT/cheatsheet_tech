---
title: Testing DRF & Factories
subtopic: django
group: Testing & CLI
order: 2
---

#### APIClient (DRF)

```python
from rest_framework.test import APITestCase, APIClient
from rest_framework import status

class PostAPITests(APITestCase):
    def setUp(self):
        self.user = User.objects.create_user('alice', password='secret')
        self.client.force_authenticate(user=self.user)

    def test_list(self):
        Post.objects.create(title='A', author=self.user)
        response = self.client.get('/api/posts/')
        self.assertEqual(response.status_code, status.HTTP_200_OK)
        self.assertEqual(len(response.data['results']), 1)

    def test_create(self):
        response = self.client.post('/api/posts/',
            {'title': 'New', 'body': 'Body', 'status': 'draft'})
        self.assertEqual(response.status_code, status.HTTP_201_CREATED)
```

#### RequestFactory & useful assertions

```python
from django.test import RequestFactory

factory = RequestFactory()
request = factory.get('/posts/')
request.user = user

# Assertions
self.assertContains(response, 'text', count=2, status_code=200)
self.assertNotContains(response, 'error')
self.assertRedirects(response, '/login/', status_code=302)
self.assertTemplateUsed(response, 'blog/post_list.html')
self.assertFormError(response, 'form', 'email', 'Enter a valid email.')
```
