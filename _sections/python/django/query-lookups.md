---
title: Query Lookups, Q & F
subtopic: django
group: Queries & Migrations
order: 5
---

#### Field lookups

```python
# Appended with __ to field names
exact   iexact          # case-insensitive
contains icontains      # LIKE %val%
startswith istartswith
endswith   iendswith
in          # field__in=[1, 2, 3]
gt  gte  lt  lte        # greater/less than
range       # field__range=(start, end)
isnull      # field__isnull=True
date year month day week_day
```

#### Q objects — complex queries

```python
from django.db.models import Q

Post.objects.filter(Q(status='published') | Q(author=user))
Post.objects.filter(Q(status='published') & ~Q(author=user))
Post.objects.filter(
    Q(title__icontains='django') | Q(body__icontains='django'))
```

#### F expressions — reference DB column

```python
from django.db.models import F

# Compare two fields or do DB-side arithmetic
Post.objects.filter(views__gt=F('likes'))
Post.objects.update(views=F('views') + 1)  # atomic increment
Post.objects.filter(updated_at__gt=F('created_at'))
```
