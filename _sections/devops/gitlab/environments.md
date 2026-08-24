---
title: Environments
subtopic: gitlab
group: Runners & Repo
order: 3
---

#### Deploy to an environment

```yaml
deploy-staging:
  stage: deploy
  script: [./deploy.sh staging]
  environment:
    name: staging
    url: https://staging.example.com
```

#### Stop action (teardown)

```yaml
deploy-staging:
  environment:
    name: staging
    on_stop: stop-staging

stop-staging:
  script: [./teardown.sh staging]
  when: manual
  environment:
    name: staging
    action: stop
```

#### Dynamic environments (e.g. per branch)

```yaml
deploy-review:
  script: [./deploy.sh]
  environment:
    name: review/$CI_COMMIT_REF_SLUG
    url: https://$CI_COMMIT_REF_SLUG.review.example.com
    on_stop: stop-review
  rules:
    - if: $CI_PIPELINE_SOURCE == "merge_request_event"
```
