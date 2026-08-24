---
title: .env Variable Substitution
subtopic: compose
group: Environment & Profiles
order: 2
---

#### Interpolating into compose.yaml itself

```
# .env (auto-loaded from the project directory)
TAG=1.0
PORT=8080
```

```yaml
services:
  web:
    image: myapp:${TAG:-latest}   # default if TAG unset
    ports:
      - "${PORT}:80"
```

This is different from `env_file:`, which only injects vars into the container.
