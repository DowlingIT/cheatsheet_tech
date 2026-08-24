---
title: Global Defaults
subtopic: gitlab
group: Pipeline Basics
order: 2
---

#### default block

```yaml
default:
  image: node:20
  tags: [docker]
  before_script:
    - npm ci
  after_script:
    - ./cleanup.sh
  retry:
    max: 2
    when: runner_system_failure
  timeout: 30 minutes
  interruptible: true
```

#### Including shared configs

```yaml
include:
  - project: org/ci-templates
    file: /templates/node.yml
  - template: Security/SAST.gitlab-ci.yml
  - local: .gitlab/ci/deploy.yml
  - remote: https://example.com/ci.yml
```
