---
title: Relationships
subtopic: django
group: Models
order: 4
---

#### ForeignKey & OneToOne

```python
# ForeignKey
author = models.ForeignKey(
    'auth.User',
    on_delete=models.CASCADE,      # PROTECT, SET_NULL, SET_DEFAULT, DO_NOTHING
    related_name='posts',          # reverse: user.posts.all()
    null=True, blank=True,
)

# OneToOne
profile = models.OneToOneField(User, on_delete=models.CASCADE,
    related_name='profile')        # reverse: user.profile
```

#### ManyToMany

```python
tags = models.ManyToManyField('Tag', blank=True,
    related_name='posts')          # post.tags.all(); tag.posts.all()

# With through model (extra fields on the join)
class PostTag(models.Model):
    post    = models.ForeignKey(Post, on_delete=models.CASCADE)
    tag     = models.ForeignKey(Tag, on_delete=models.CASCADE)
    added_at = models.DateTimeField(auto_now_add=True)

tags = models.ManyToManyField('Tag', through='PostTag')
```

#### Reverse access

```python
user.posts.all()                    # ForeignKey reverse
user.posts.filter(status='published').count()
post.tags.add(tag)                  # M2M add/remove/set/clear
post.tags.set([tag1, tag2])
```
