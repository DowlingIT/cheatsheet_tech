---
title: Responses & Rendering
subtopic: django
group: Views & Forms
order: 3
render_with_liquid: false
---

#### Response types

```python
from django.http import (
    HttpResponse, HttpResponseRedirect,
    HttpResponseNotFound, HttpResponseForbidden,
    JsonResponse, StreamingHttpResponse, FileResponse,
)
from django.shortcuts import render, render_to_string

HttpResponse('Hello', content_type='text/plain', status=200)
JsonResponse({'ok': True})
JsonResponse(list(qs.values()), safe=False)  # non-dict

# File download
response = FileResponse(open('report.pdf', 'rb'))
response['Content-Disposition'] = 'attachment; filename="report.pdf"'
```

#### Shortcuts & errors

```python
from django.shortcuts import get_object_or_404, get_list_or_404
from django.core.exceptions import PermissionDenied
from django.http import Http404

post = get_object_or_404(Post, pk=pk, status='published')

if not request.user.can_edit(post):
    raise PermissionDenied

raise Http404('Post not found')

# Render to string (email bodies, PDF, etc.)
html = render_to_string('emails/welcome.html', {'user': user},
                         request=request)
```

#### Messages framework

```python
from django.contrib import messages

messages.success(request, 'Post published.')
messages.error(request, 'Something went wrong.')
messages.warning(request, 'This action is irreversible.')

# In template:
# {% for msg in messages %}{{ msg }}{% endfor %}
```
