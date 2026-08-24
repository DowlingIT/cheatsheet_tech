---
title: Pipeline Structure
subtopic: bitbucket
group: Pipelines
order: 1
---

#### File location

`bitbucket-pipelines.yml` (repo root)

#### Minimal example

```yaml
image: node:20

pipelines:
  default:
    - step:
        name: Build & Test
        caches:
          - node
        script:
          - npm ci
          - npm test
```

#### Image options

```yaml
image: node:20-alpine
image: python:3.12

image:
  name: registry.example.com/myimage:tag
  username: $REGISTRY_USER
  password: $REGISTRY_PASS
  aws:
    access-key: $AWS_ACCESS_KEY
    secret-key: $AWS_SECRET_KEY
```
