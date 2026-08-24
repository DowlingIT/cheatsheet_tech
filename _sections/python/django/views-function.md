---
title: Function-Based Views
subtopic: django
group: Views & Forms
order: 1
---

#### FBV pattern

```python
from django.shortcuts import render, get_object_or_404, redirect
from django.http import JsonResponse

def post_list(request):
    posts = Post.objects.filter(published=True).order_by('-created_at')
    return render(request, 'blog/post_list.html', {'posts': posts})

def post_detail(request, pk):
    post = get_object_or_404(Post, pk=pk)
    return render(request, 'blog/post_detail.html', {'post': post})

def post_create(request):
    if request.method == 'POST':
        form = PostForm(request.POST)
        if form.is_valid():
            post = form.save()
            return redirect(post)
    else:
        form = PostForm()
    return render(request, 'blog/post_form.html', {'form': form})
```
