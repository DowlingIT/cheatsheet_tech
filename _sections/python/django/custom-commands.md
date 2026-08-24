---
title: Custom Commands
subtopic: django
group: Testing & CLI
order: 2
---

#### Command structure

```python
# myapp/management/commands/send_reminders.py
from django.core.management.base import BaseCommand
from django.contrib.auth import get_user_model

class Command(BaseCommand):
    help = 'Sends reminder emails to inactive users'

    def add_arguments(self, parser):
        parser.add_argument('days', type=int)
        parser.add_argument('--dry-run', action='store_true')

    def handle(self, *args, **options):
        User    = get_user_model()
        days    = options['days']
        dry_run = options['dry_run']
        users   = User.objects.filter(last_login__isnull=True)
        if not dry_run:
            for user in users:
                send_reminder(user)
        self.stdout.write(
            self.style.SUCCESS(f'Done: {users.count()} users'))
```

#### Run

```bash
python manage.py send_reminders 30
python manage.py send_reminders 30 --dry-run
```
