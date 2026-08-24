---
title: Static & Media Files
subtopic: django
group: Settings & Static
order: 1
render_with_liquid: false
---

#### Settings

```python
# Static files (CSS, JS, images bundled with the app)
STATIC_URL       = '/static/'
STATICFILES_DIRS = [BASE_DIR / 'static']   # extra source dirs
STATIC_ROOT      = BASE_DIR / 'staticfiles' # collectstatic destination

# Media files (user uploads)
MEDIA_URL  = '/media/'
MEDIA_ROOT = BASE_DIR / 'media'
```

#### Serve media in development

```python
# urls.py (dev only — never in production)
from django.conf import settings
from django.conf.urls.static import static

urlpatterns = [...] + static(settings.MEDIA_URL,
                              document_root=settings.MEDIA_ROOT)
```

#### In templates

```django
{% load static %}

<link rel="stylesheet" href="{% static 'css/app.css' %}">
<script src="{% static 'js/main.js' %}"></script>
<img src="{% static 'images/logo.png' %}" alt="Logo">

{# User-uploaded file from model #}
<img src="{{ post.image.url }}" alt="{{ post.title }}">
```

#### collectstatic

```bash
python manage.py collectstatic   # copies all static files to STATIC_ROOT
# In production serve STATIC_ROOT with nginx/whitenoise
```
