---
title: Middleware
subtopic: django
group: Settings & Static
order: 2
---

#### Writing middleware

```python
import time

class TimingMiddleware:
    def __init__(self, get_response):
        self.get_response = get_response   # called once on startup

    def __call__(self, request):
        start    = time.monotonic()
        response = self.get_response(request)  # next layer / view
        elapsed  = time.monotonic() - start
        response['X-Request-Time'] = f'{elapsed:.3f}s'
        return response

    def process_exception(self, request, exception):
        # return a Response to handle, or None to propagate
        pass
```

#### Registration (settings.py)

```python
MIDDLEWARE = [
    'django.middleware.security.SecurityMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.middleware.common.CommonMiddleware',
    'django.middleware.csrf.CsrfViewMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'myapp.middleware.TimingMiddleware',    # custom — add here
]
```
