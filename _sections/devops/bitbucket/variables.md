---
title: Variables
subtopic: bitbucket
group: Config
order: 1
---

#### Predefined variables

```
$BITBUCKET_COMMIT           # full commit SHA
$BITBUCKET_BRANCH           # branch name
$BITBUCKET_TAG              # tag (if triggered by tag)
$BITBUCKET_BUILD_NUMBER     # unique build counter
$BITBUCKET_REPO_SLUG        # repo name
$BITBUCKET_WORKSPACE        # workspace slug
$BITBUCKET_PR_ID            # pull request number
$BITBUCKET_DEPLOYMENT_ENVIRONMENT
```

#### Custom variables (manual pipelines)

```yaml
custom:
  deploy:
    variables:
      - name: TARGET_ENV
        default: staging
        allowed-values:
          - staging
          - production
    - step:
        script: [./deploy.sh $TARGET_ENV]
```

#### Variable scopes

- **Workspace** — available across all repos in the workspace
- **Repository** — repo-level, set in Repository Settings → Variables
- **Deployment** — environment-specific, override repository vars
