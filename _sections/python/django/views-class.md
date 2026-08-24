---
title: Class-Based Views
subtopic: django
group: Views & Forms
order: 2
---

#### Generic CBVs

```python
from django.views.generic import (
    ListView, DetailView,
    CreateView, UpdateView, DeleteView,
)
from django.urls import reverse_lazy

class PostListView(ListView):
    model = Post
    template_name = 'blog/post_list.html'
    context_object_name = 'posts'
    paginate_by = 10

    def get_queryset(self):
        return Post.objects.filter(published=True)

class PostCreateView(CreateView):
    model = Post
    fields = ['title', 'body', 'status']
    success_url = reverse_lazy('post-list')

    def form_valid(self, form):
        form.instance.author = self.request.user
        return super().form_valid(form)
```

#### URL wiring

```python
path('posts/', PostListView.as_view(), name='post-list'),
path('posts/new/', PostCreateView.as_view(), name='post-create'),
path('posts/<int:pk>/', PostDetailView.as_view(), name='post-detail'),
path('posts/<int:pk>/delete/', PostDeleteView.as_view(), name='post-delete'),
```
