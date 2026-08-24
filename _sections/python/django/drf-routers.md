---
title: DRF Routers & Setup
subtopic: django
group: DRF
order: 3
---

#### Router URL registration

```python
# urls.py
from rest_framework.routers import DefaultRouter
from .views import PostViewSet, TagViewSet

router = DefaultRouter()
router.register('posts', PostViewSet, basename='post')
router.register('tags',  TagViewSet,  basename='tag')

urlpatterns = [
    path('api/', include(router.urls)),
]
# Generated routes:
# GET/POST  /api/posts/
# GET/PUT/PATCH/DELETE  /api/posts/{pk}/
# POST      /api/posts/{pk}/publish/   (extra @action)
```

#### settings.py (DRF defaults)

```python
REST_FRAMEWORK = {
    'DEFAULT_AUTHENTICATION_CLASSES': [
        'rest_framework.authentication.SessionAuthentication',
        'rest_framework_simplejwt.authentication.JWTAuthentication',
    ],
    'DEFAULT_PERMISSION_CLASSES': [
        'rest_framework.permissions.IsAuthenticatedOrReadOnly',
    ],
    'DEFAULT_PAGINATION_CLASS': 'rest_framework.pagination.PageNumberPagination',
    'PAGE_SIZE': 20,
    'DEFAULT_FILTER_BACKENDS': [
        'django_filters.rest_framework.DjangoFilterBackend',
        'rest_framework.filters.SearchFilter',
        'rest_framework.filters.OrderingFilter',
    ],
}
```
