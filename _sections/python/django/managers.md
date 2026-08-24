---
title: Custom Managers
subtopic: django
group: Models
order: 6
---

#### Custom Manager & QuerySet

```python
class PublishedQuerySet(models.QuerySet):
    def published(self):
        return self.filter(status='published')

    def by_author(self, user):
        return self.filter(author=user)

class PostManager(models.Manager):
    def get_queryset(self):
        return PublishedQuerySet(self.model, using=self._db)

    def published(self):
        return self.get_queryset().published()

class Post(models.Model):
    objects  = PostManager()

    # usage:
    # Post.objects.published()
    # Post.objects.published().by_author(user)
```

#### Model methods & save override

```python
class Post(models.Model):
    def clean(self):
        if self.status == 'published' and not self.slug:
            raise ValidationError('Published posts need a slug')

    def save(self, *args, **kwargs):
        if not self.slug:
            self.slug = slugify(self.title)
        super().save(*args, **kwargs)

    @property
    def is_published(self) -> bool:
        return self.status == 'published'
```
