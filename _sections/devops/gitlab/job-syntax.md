---
title: Job Syntax
subtopic: gitlab
group: Jobs
order: 1
---

#### Job options

```yaml
my-job:
  stage: test
  image: node:20
  tags: [docker, linux]
  when: on_success       # always, on_failure, manual, delayed, never
  allow_failure: true
  timeout: 30 minutes
  retry:
    max: 2
    when: runner_system_failure
  interruptible: true    # cancel on new pipeline push
  script:
    - npm test
```

#### Before/after script

```yaml
default:
  before_script:
    - npm ci              # runs before every job's script

my-job:
  script: [npm test]
  after_script:           # always runs, even on failure
    - ./notify.sh
```
