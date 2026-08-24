---
title: Email
subtopic: django
group: Caching & Email
order: 2
---

#### settings.py

```python
EMAIL_BACKEND = 'django.core.mail.backends.smtp.EmailBackend'
EMAIL_HOST     = 'smtp.gmail.com'
EMAIL_PORT     = 587
EMAIL_USE_TLS  = True
EMAIL_HOST_USER     = env('EMAIL_HOST_USER')
EMAIL_HOST_PASSWORD = env('EMAIL_HOST_PASSWORD')
DEFAULT_FROM_EMAIL  = 'noreply@example.com'

# Development backends
EMAIL_BACKEND = 'django.core.mail.backends.console.EmailBackend'
EMAIL_BACKEND = 'django.core.mail.backends.filebased.EmailBackend'
EMAIL_FILE_PATH = BASE_DIR / 'sent_emails'
```

#### Sending email

```python
from django.core.mail import send_mail, send_mass_mail, EmailMessage

send_mail(
    subject='Welcome!',
    message='Thanks for signing up.',
    from_email='noreply@example.com',
    recipient_list=['user@example.com'],
    html_message='<p>Thanks for <strong>signing up</strong>.</p>',
)

# Full control
msg = EmailMessage(
    subject='Order confirmation',
    body='Your order has shipped.',
    from_email='noreply@example.com',
    to=['user@example.com'],
    cc=['sales@example.com'],
)
msg.attach_file('invoice.pdf')
msg.send()
```
