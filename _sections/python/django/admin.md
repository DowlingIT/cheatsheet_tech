---
title: Django Admin
subtopic: django
group: Admin
order: 1
---

#### Registration & customization

```python
from django.contrib import admin
from .models import Post

@admin.register(Post)
class PostAdmin(admin.ModelAdmin):
    list_display        = ['title', 'author', 'status', 'created_at']
    list_filter         = ['status', 'created_at', 'author']
    search_fields       = ['title', 'body']
    prepopulated_fields = {'slug': ('title',)}
    raw_id_fields       = ['author']
    date_hierarchy      = 'created_at'
    ordering            = ['-created_at']
    readonly_fields     = ['created_at', 'updated_at']

    def get_queryset(self, request):
        return super().get_queryset(request).select_related('author')

    @admin.action(description='Mark selected posts as published')
    def publish(self, request, queryset):
        queryset.update(status='published')

    actions = [publish]
```
