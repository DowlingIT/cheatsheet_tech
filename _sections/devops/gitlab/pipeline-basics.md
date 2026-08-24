---
title: Pipeline Structure
subtopic: gitlab
group: Pipeline Basics
order: 1
---

#### File location

`.gitlab-ci.yml` (repo root)

#### Minimal example

```yaml
stages:
  - build
  - test
  - deploy

build:
  stage: build
  script:
    - npm ci
    - npm run build
  artifacts:
    paths: [dist/]

test:
  stage: test
  script: [npm test]

deploy:
  stage: deploy
  script: [./deploy.sh]
  rules:
    - if: $CI_COMMIT_BRANCH == "main"
```
