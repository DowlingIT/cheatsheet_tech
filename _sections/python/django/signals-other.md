---
title: Request & Migration Signals
subtopic: django
group: Queries & Migrations
order: 5
---

#### Request / response signals

```python
from django.core.signals import (
    request_started,    # fires before Django begins processing a request
    request_finished,   # fires after response is delivered to client
    got_request_exception,  # fires when an unhandled exception occurs
)
from django.dispatch import receiver

@receiver(request_started)
def on_request_started(sender, environ, **kwargs):
    pass    # environ is the WSGI/ASGI environ dict

@receiver(got_request_exception)
def on_exception(sender, request, **kwargs):
    pass
```

#### Migration & test signals

```python
from django.db.models.signals import pre_migrate, post_migrate

@receiver(post_migrate)
def create_default_groups(sender, **kwargs):
    # runs after every migrate — safe to create initial data here
    Group.objects.get_or_create(name='editors')

# setting_changed — fires when override_settings() changes a value (tests)
from django.test.signals import setting_changed

@receiver(setting_changed)
def reload_config(sender, setting, value, enter, **kwargs):
    if setting == 'MY_CONFIG':
        reload_my_config()
```
