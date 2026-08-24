---
title: File Structure
subtopic: django
group: Overview
order: 1
---

#### Project layout

```
myproject/
  manage.py               CLI entry point
  myproject/              project package (same name as project)
    settings.py           configuration
    urls.py               root URL conf
    wsgi.py               WSGI entrypoint (sync)
    asgi.py               ASGI entrypoint (async)

  myapp/                  a typical app
    models.py             database models
    views.py              view functions / CBVs
    urls.py               app URL conf
    forms.py              form classes
    admin.py              admin registration
    apps.py               AppConfig class
    tests.py              tests
    migrations/           auto-generated migration files
    templates/myapp/      app-level HTML templates
    static/myapp/         CSS, JS, images
    serializers.py        DRF serializers (if building an API)

  templates/              project-level shared templates
  static/                 project-level shared static files
  requirements.txt        or pyproject.toml
  .env                    environment variables (never commit)
```
