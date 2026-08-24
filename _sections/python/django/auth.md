---
title: Authentication
subtopic: django
group: Auth & Users
order: 1
---

#### Decorators & mixins

```python
from django.contrib.auth.decorators import login_required, permission_required
from django.contrib.auth.mixins import LoginRequiredMixin, PermissionRequiredMixin

@login_required
def dashboard(request): ...

@login_required(login_url='/accounts/login/')
def profile(request): ...

@permission_required('blog.change_post', raise_exception=True)
def edit_post(request, pk): ...

class PostUpdateView(LoginRequiredMixin, UpdateView):
    login_url = '/login/'
```

#### Auth operations

```python
from django.contrib import auth

user = auth.authenticate(request, username=u, password=p)
if user:
    auth.login(request, user)

auth.logout(request)

request.user.is_authenticated
request.user.has_perm('blog.add_post')
request.user.has_perms(['blog.add_post', 'blog.change_post'])

# Built-in auth URLs (login, logout, password reset/change)
path('accounts/', include('django.contrib.auth.urls')),
```
