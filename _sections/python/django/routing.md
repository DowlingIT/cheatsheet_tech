---
title: URL Patterns
subtopic: django
group: URL Routing
order: 1
---

#### urls.py

```python
from django.urls import path, re_path, include

urlpatterns = [
    path('posts/', views.post_list, name='post-list'),
    path('posts/<int:pk>/', views.post_detail, name='post-detail'),
    path('posts/<slug:slug>/', views.post_by_slug, name='post-slug'),
    re_path(r'^archive/(?P<year>[0-9]{4})/$', views.archive),

    path('blog/', include('blog.urls')),
    path('api/', include(('api.urls', 'api'), namespace='api')),
]
```

#### Path converters

```
<int:pk>      integer (positive)
<str:name>    non-empty string, no /
<slug:slug>   letters, numbers, hyphens, underscores
<uuid:id>     UUID string
<path:rest>   any string including /
```
