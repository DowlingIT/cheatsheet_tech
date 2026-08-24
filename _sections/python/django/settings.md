---
title: settings.py
subtopic: django
group: Settings & Static
order: 1
---

#### Core settings

```python
from pathlib import Path
import environ

BASE_DIR   = Path(__file__).resolve().parent.parent
env        = environ.Env()
environ.Env.read_env(BASE_DIR / '.env')

SECRET_KEY    = env('SECRET_KEY')
DEBUG         = env.bool('DEBUG', default=False)
ALLOWED_HOSTS = env.list('ALLOWED_HOSTS')

AUTH_USER_MODEL     = 'accounts.User'
DEFAULT_AUTO_FIELD  = 'django.db.models.BigAutoField'
LANGUAGE_CODE = 'en-us'
TIME_ZONE     = 'UTC'
USE_I18N = True
USE_TZ   = True
```

#### Database, static & media

```python
DATABASES = {'default': env.db()}  # reads DATABASE_URL env var

STATIC_URL       = '/static/'
STATICFILES_DIRS = [BASE_DIR / 'static']
STATIC_ROOT      = BASE_DIR / 'staticfiles'
MEDIA_URL  = '/media/'
MEDIA_ROOT = BASE_DIR / 'media'
```

#### Email & cache

```python
EMAIL_BACKEND = env('EMAIL_BACKEND',
    default='django.core.mail.backends.console.EmailBackend')
EMAIL_HOST     = env('EMAIL_HOST', default='localhost')
EMAIL_PORT     = env.int('EMAIL_PORT', default=587)
EMAIL_USE_TLS  = True
DEFAULT_FROM_EMAIL = env('DEFAULT_FROM_EMAIL', default='noreply@localhost')

CACHES = {'default': env.cache(default='locmemcache://')}
SESSION_ENGINE = 'django.contrib.sessions.backends.cache'
```

#### Logging

```python
LOGGING = {
    'version': 1,
    'disable_existing_loggers': False,
    'handlers': {
        'console': {'class': 'logging.StreamHandler'},
        'file': {'class': 'logging.FileHandler', 'filename': 'django.log'},
    },
    'root': {'handlers': ['console'], 'level': 'WARNING'},
    'loggers': {
        'django': {'handlers': ['file'], 'level': 'INFO', 'propagate': False},
        'myapp':  {'handlers': ['console'], 'level': 'DEBUG', 'propagate': False},
    },
}
```
