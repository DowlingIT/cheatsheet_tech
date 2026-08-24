---
title: Caches & Artifacts
subtopic: bitbucket
group: Steps & Caches
order: 2
---

#### Built-in cache keys

```yaml
caches:
  - node          # ~/.npm
  - pip           # ~/.cache/pip
  - composer      # ~/.composer/cache
  - maven         # ~/.m2/repository
  - gradle        # ~/.gradle/caches
  - docker        # /var/lib/docker
```

#### Custom cache definition

```yaml
definitions:
  caches:
    npm-modules:
      key:
        files:
          - package-lock.json
      path: node_modules

pipelines:
  default:
    - step:
        caches: [npm-modules]
        script: [npm ci]
```

#### Artifacts between steps

```yaml
- step:
    script: [npm run build]
    artifacts:
      - dist/**             # available to all subsequent steps

- step:
    script: [./deploy.sh]   # dist/ is present
```
