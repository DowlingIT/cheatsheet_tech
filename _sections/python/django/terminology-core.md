---
title: Core Concepts
subtopic: django
group: Overview
order: 1
---

#### MTV pattern

```
MTV = Model-View-Template  (Django's variant of MVC)

Model       data structure and database access (ORM)
View        business logic — receives request, returns response
Template    HTML presentation layer rendered by a view
URL conf    maps URL patterns to views (urls.py)
App         self-contained feature module with its own models/views/urls
Project     collection of apps + settings (manage.py lives here)
```

#### Request lifecycle

```
urls.py → middleware → view → ORM → template → response → middleware
```

#### Key files

```
manage.py           CLI entry point — runserver, migrate, shell
settings.py         INSTALLED_APPS, DATABASES, MIDDLEWARE, TEMPLATES
wsgi.py / asgi.py   server entrypoints (sync / async)
urls.py             root URL configuration
apps.py             AppConfig class — register signals, run startup logic
```
