---
title: Model Definition
subtopic: django
group: Models
order: 1
---

#### Model anatomy

```python
from django.db import models

class Post(models.Model):
    author   = models.ForeignKey('auth.User', on_delete=models.CASCADE,
                                  related_name='posts')
    title    = models.CharField(max_length=200)
    slug     = models.SlugField(unique=True)
    body     = models.TextField()
    status   = models.CharField(max_length=10,
                 choices=[('draft', 'Draft'), ('published', 'Published')],
                 default='draft')
    tags     = models.ManyToManyField('Tag', blank=True)
    created_at = models.DateTimeField(auto_now_add=True)
    updated_at = models.DateTimeField(auto_now=True)

    class Meta:
        ordering = ['-created_at']
        indexes  = [models.Index(fields=['slug'])]
        verbose_name_plural = 'posts'

    def __str__(self):
        return self.title
```
