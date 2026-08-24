---
title: environment & env_file
subtopic: compose
group: Environment & Profiles
order: 1
---

#### Passing variables into a service

```yaml
services:
  web:
    environment:
      NODE_ENV: production
      API_KEY: ${API_KEY}       # pulled from shell or .env
    env_file:
      - .env.production
```

`environment:` entries win over `env_file:` entries when both set the same key.
