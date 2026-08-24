---
title: Pipeline Triggers
subtopic: bitbucket
group: Pipelines
order: 1
---

#### Branch-specific pipelines

```yaml
pipelines:
  default:                      # all unmatched branches
    - step:
        script: [npm test]

  branches:
    main:
      - step:
          script: [npm run deploy:prod]
    develop:
      - step:
          script: [npm run deploy:staging]
    'feature/*':
      - step:
          script: [npm test]
```

#### Tags, PRs & manual

```yaml
  tags:
    'v*':
      - step:
          script: [npm run release]

  pull-requests:
    '**':
      - step:
          script: [npm test]

  custom:
    deploy-prod:                # triggered manually from UI
      - step:
          script: [npm run deploy:prod]
```
