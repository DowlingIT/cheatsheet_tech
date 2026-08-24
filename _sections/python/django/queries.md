---
title: QuerySet API
subtopic: django
group: Queries & Migrations
order: 2
---

#### Retrieve

```python
Post.objects.all()
Post.objects.get(pk=1)                   # raises DoesNotExist
Post.objects.filter(status='published')
Post.objects.exclude(status='draft')
Post.objects.filter(title__icontains='django')
Post.objects.filter(created_at__year=2024)
Post.objects.filter(author__username='alice')  # follow FK
Post.objects.order_by('-created_at')[:10]
Post.objects.select_related('author')          # SQL JOIN (FK)
Post.objects.prefetch_related('tags')          # IN query (M2M)
```

#### Write & aggregate

```python
Post.objects.create(title='Hello', author=user)
Post.objects.filter(status='draft').update(status='published')
Post.objects.filter(pk__in=[1, 2, 3]).delete()

post, created = Post.objects.get_or_create(
    slug='hello', defaults={'title': 'Hello'})

Post.objects.bulk_create([Post(title='a'), Post(title='b')])

from django.db.models import Count, Avg
Post.objects.aggregate(total=Count('id'), avg_views=Avg('views'))
Post.objects.values('status').annotate(count=Count('id'))
```
