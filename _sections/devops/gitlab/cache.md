---
title: Caching
subtopic: gitlab
group: Artifacts & Cache
order: 2
---

#### Cache definition

```yaml
my-job:
  cache:
    key: $CI_COMMIT_REF_SLUG
    paths:
      - node_modules/
      - .npm/
    policy: pull-push       # pull, push, or pull-push (default)
```

#### Lock cache to lockfile changes

```yaml
cache:
  key:
    files:
      - package-lock.json
  paths:
    - node_modules/
```

#### Global default + per-job override

```yaml
default:
  cache:
    key: global-npm
    paths: [.npm/]
    policy: pull            # most jobs only read

build:
  cache:
    policy: pull-push       # only the build job writes new cache
```
