---
title: Inline Admin
subtopic: django
group: Admin
order: 2
---

#### TabularInline & StackedInline

```python
from django.contrib import admin
from .models import Post, Comment

class CommentInline(admin.TabularInline):  # or StackedInline
    model   = Comment
    extra   = 1          # number of empty forms shown
    max_num = 10
    can_delete = True
    fields  = ['author', 'body', 'approved']
    readonly_fields = ['created_at']

    def get_queryset(self, request):
        return super().get_queryset(request).select_related('author')

@admin.register(Post)
class PostAdmin(admin.ModelAdmin):
    inlines = [CommentInline]
```

#### GenericTabularInline (ContentTypes)

```python
from django.contrib.contenttypes.admin import GenericTabularInline
from .models import Image

class ImageInline(GenericTabularInline):
    model = Image
    extra = 1
```
