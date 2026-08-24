---
title: Variables
subtopic: gitlab
group: Variables
order: 1
---

#### Define in pipeline

```yaml
variables:
  DEPLOY_ENV: staging
  NODE_ENV: production

my-job:
  variables:
    LOCAL_VAR: value      # job-level, overrides global
  script: [echo $DEPLOY_ENV]
```

#### Variable types (set in UI)

- **Variable** — injected as an environment variable
- **File** — written to a temp file; `$VAR` holds the path
- **Masked** — hidden in job logs (value must match masking rules)
- **Protected** — only available on protected branches and tags
- **Expanded** — allows `$OTHER_VAR` references inside the value

#### Pass values between jobs via dotenv

```yaml
build:
  script:
    - echo "SHA=$(git rev-parse --short HEAD)" >> build.env
  artifacts:
    reports:
      dotenv: build.env

deploy:
  needs:
    - job: build
      artifacts: true
  script:
    - echo "Deploying $SHA"
```
