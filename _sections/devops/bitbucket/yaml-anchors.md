---
title: YAML Anchors
subtopic: bitbucket
group: Pipelines
order: 3
---

#### Define & reuse steps

```yaml
definitions:
  steps:
    - step: &install-test
        name: Install & Test
        caches: [node]
        script:
          - npm ci
          - npm test

pipelines:
  default:
    - step: *install-test

  branches:
    main:
      - step: *install-test
      - step:
          name: Deploy
          script: [./deploy.sh]
```

#### Merge with overrides

```yaml
definitions:
  steps:
    - step: &base-step
        image: node:20
        caches: [node]
        script: [npm ci]

pipelines:
  default:
    - step:
        <<: *base-step         # inherit all keys
        name: Test             # override or add keys
        script:
          - npm ci
          - npm test
```
