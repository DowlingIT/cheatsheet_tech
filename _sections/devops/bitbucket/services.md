---
title: Services
subtopic: bitbucket
group: Steps & Caches
order: 3
---

#### Sidecar service containers

```yaml
definitions:
  services:
    postgres:
      image: postgres:16
      variables:
        POSTGRES_DB: testdb
        POSTGRES_USER: user
        POSTGRES_PASSWORD: pass
    redis:
      image: redis:7

pipelines:
  default:
    - step:
        services:
          - postgres
          - redis
        script:
          - npm test
```

#### Docker-in-Docker

```yaml
- step:
    services:
      - docker
    script:
      - docker build -t myapp .
      - docker push myapp
```
