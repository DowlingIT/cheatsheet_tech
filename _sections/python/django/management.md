---
title: manage.py Commands
subtopic: django
group: Testing & CLI
order: 1
---

#### Development & database

```bash
python manage.py runserver              # dev server on :8000
python manage.py runserver 0.0.0.0:8080
python manage.py shell                  # interactive Python shell
python manage.py dbshell                # database CLI

python manage.py startproject myproject
python manage.py startapp myapp

python manage.py makemigrations
python manage.py migrate
python manage.py showmigrations
python manage.py dumpdata myapp.Post --indent 2 > posts.json
python manage.py loaddata posts.json
python manage.py createsuperuser
```

#### Static files & checks

```bash
python manage.py collectstatic    # gather to STATIC_ROOT
python manage.py check            # run system checks
python manage.py test myapp
python manage.py test myapp.tests.PostTests
```
