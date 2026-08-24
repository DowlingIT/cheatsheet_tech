---
title: Needs & Parallel
subtopic: gitlab
group: Jobs
order: 3
---

#### DAG with needs

```yaml
# Starts as soon as build finishes, skips waiting for other stage jobs
test:
  stage: test
  needs: [build]
  script: [npm test]
```

#### Download artifacts from specific jobs

```yaml
deploy:
  needs:
    - job: build
      artifacts: true
    - job: security-scan
      artifacts: false
  script: [./deploy.sh dist/]
```

#### Parallel job splitting

```yaml
test:
  parallel: 5               # creates 5 instances: 1/5, 2/5, …
  script:
    - ./run-tests.sh $CI_NODE_INDEX $CI_NODE_TOTAL
```
