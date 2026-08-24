---
title: Custom User Model
subtopic: django
group: Auth & Users
order: 1
---

#### AbstractUser (extend the default)

```python
# accounts/models.py
from django.contrib.auth.models import AbstractUser

class User(AbstractUser):
    bio    = models.TextField(blank=True)
    avatar = models.ImageField(upload_to='avatars/', blank=True)

    def get_full_name(self):
        return f'{self.first_name} {self.last_name}'.strip()
```

#### settings.py

```python
AUTH_USER_MODEL = 'accounts.User'   # must be set BEFORE first migration
```

#### Admin registration

```python
from django.contrib.auth.admin import UserAdmin
from .models import User

@admin.register(User)
class CustomUserAdmin(UserAdmin):
    fieldsets = UserAdmin.fieldsets + (
        ('Profile', {'fields': ('bio', 'avatar')}),
    )
    add_fieldsets = UserAdmin.add_fieldsets + (
        ('Profile', {'fields': ('bio',)}),
    )
```

#### Referencing the user model

```python
from django.conf import settings
from django.contrib.auth import get_user_model

User = get_user_model()   # always use this, not a direct import
author = models.ForeignKey(settings.AUTH_USER_MODEL, on_delete=models.CASCADE)
```
