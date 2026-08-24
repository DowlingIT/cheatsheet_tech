---
title: Deployments
subtopic: bitbucket
group: Config
order: 1
---

#### Environment types

```yaml
# deployment: controls which environment bucket the step targets
deployment: test          # Test environments
deployment: staging       # Staging environments
deployment: production    # Production environments
```

#### Deployment step

```yaml
- step:
    name: Deploy to Production
    deployment: production
    trigger: manual
    script:
      - npm run deploy
```

#### Environment variables

Set in **Repository Settings → Deployments**. Environment-level variables override repository-level variables when `deployment:` is set on the step. Useful for environment-specific API keys, URLs, and credentials.
