---
title: Secrets
subtopic: compose
group: Environment & Profiles
order: 4
---

#### File-based secrets

```yaml
secrets:
  db_password:
    file: ./secrets/db_password.txt

services:
  db:
    image: postgres:16
    secrets:
      - db_password
    environment:
      POSTGRES_PASSWORD_FILE: /run/secrets/db_password
```

Mounted read-only as a file at `/run/secrets/<name>` inside the
container — never passed as a plain environment variable.
