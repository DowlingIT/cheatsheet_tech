---
title: Signals
subtopic: django
group: Queries & Migrations
order: 1
---

#### Built-in model signals

```python
from django.db.models.signals import (
    pre_save, post_save,
    pre_delete, post_delete,
    m2m_changed,
)
from django.dispatch import receiver

@receiver(post_save, sender=Post)
def on_post_save(sender, instance, created, **kwargs):
    if created:
        notify_subscribers(instance)

@receiver(pre_delete, sender=Post)
def on_post_delete(sender, instance, **kwargs):
    instance.cleanup_media()
```

#### Registration in AppConfig

```python
# myapp/apps.py
class MyAppConfig(AppConfig):
    name = 'myapp'

    def ready(self):
        import myapp.signals   # import to connect receivers

# myapp/__init__.py
default_app_config = 'myapp.apps.MyAppConfig'
```

#### Custom signals

```python
from django.dispatch import Signal

order_placed = Signal()

# Fire
order_placed.send(sender=Order, order=instance, user=request.user)

# Receive
@receiver(order_placed)
def handle_order(sender, order, user, **kwargs):
    send_confirmation_email(user, order)
```
