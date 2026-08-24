---
title: URL Helpers
subtopic: django
group: URL Routing
order: 2
render_with_liquid: false
---

#### Reverse URLs in Python

```python
from django.urls import reverse

reverse('post-detail', args=[42])
reverse('post-detail', kwargs={'pk': 42})
reverse('api:post-list')           # namespaced URL
```

#### In templates

```django
{% url 'post-detail' pk=post.pk %}
{% url 'api:post-list' %}
```

#### On models & redirects

```python
class Post(models.Model):
    def get_absolute_url(self):
        return reverse('post-detail', kwargs={'pk': self.pk})

# views.py
from django.shortcuts import redirect
return redirect('post-list')
return redirect('post-detail', pk=post.pk)
return redirect(post)          # calls get_absolute_url()
return redirect('/absolute/')
```
