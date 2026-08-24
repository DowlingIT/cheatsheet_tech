---
title: Rules & Conditions
subtopic: gitlab
group: Jobs
order: 2
---

#### rules (preferred over only/except)

```yaml
deploy:
  script: [./deploy.sh]
  rules:
    - if: $CI_COMMIT_BRANCH == "main"
      when: on_success
    - if: $CI_PIPELINE_SOURCE == "merge_request_event"
      when: manual
    - if: $CI_COMMIT_TAG
      variables:
        DEPLOY_ENV: production
    - when: never               # skip in all other cases
```

#### Legacy only/except

```yaml
my-job:
  only:
    - main
    - tags
  except:
    - schedules
```

#### Useful rule conditions

```yaml
if: $CI_PIPELINE_SOURCE == "schedule"
if: $CI_COMMIT_BRANCH =~ /^feature\/.+/
if: $CI_MERGE_REQUEST_TARGET_BRANCH_NAME == "main"
```
