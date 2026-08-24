---
title: Admin Display & Fieldsets
subtopic: django
group: Admin
order: 3
---

#### Fieldsets & list_editable

```python
@admin.register(Post)
class PostAdmin(admin.ModelAdmin):
    fieldsets = [
        (None,        {'fields': ['title', 'slug', 'author']}),
        ('Content',   {'fields': ['body', 'status'],
                       'classes': ['collapse']}),
        ('Metadata',  {'fields': ['created_at', 'updated_at'],
                       'classes': ['collapse']}),
    ]
    list_editable    = ['status']
    list_display_links = ['title']   # clickable column(s)
    list_per_page    = 25
    save_on_top      = True
```

#### Custom list_display columns

```python
@admin.register(Post)
class PostAdmin(admin.ModelAdmin):
    list_display = ['title', 'author', 'status', 'word_count']

    @admin.display(description='Words', ordering='body')
    def word_count(self, obj):
        return len(obj.body.split())

    @admin.display(description='Published', boolean=True)
    def is_published(self, obj):
        return obj.status == 'published'
```
