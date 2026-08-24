---
title: Migrations
subtopic: django
group: Queries & Migrations
order: 1
---

#### Commands

```bash
python manage.py makemigrations           # detect model changes
python manage.py makemigrations myapp     # specific app
python manage.py migrate                  # apply all pending
python manage.py migrate myapp 0003       # migrate to specific
python manage.py migrate myapp zero       # unapply all app migrations
python manage.py showmigrations           # list with applied status
python manage.py sqlmigrate myapp 0001    # preview SQL
python manage.py squashmigrations myapp 0001 0010
```

#### Migration file structure

```python
class Migration(migrations.Migration):
    dependencies = [('myapp', '0001_initial')]

    operations = [
        migrations.AddField(
            model_name='post',
            name='excerpt',
            field=models.TextField(blank=True, default=''),
        ),
        migrations.AlterField(
            model_name='post',
            name='status',
            field=models.CharField(max_length=20, default='draft'),
        ),
        migrations.RunPython(populate_slugs, reverse_code=migrations.RunPython.noop),
    ]
```
