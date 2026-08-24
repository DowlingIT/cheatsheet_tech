---
title: Trigger Events
subtopic: github
group: Workflows
order: 1
---

#### Push & pull request

```yaml
on:
  push:
    branches: [main, develop]
    paths: ['src/**']
    tags: ['v*']
  pull_request:
    branches: [main]
    types: [opened, synchronize, reopened]
```

#### Schedule & manual

```yaml
on:
  schedule:
    - cron: '0 6 * * 1'    # Mon 6am UTC
  workflow_dispatch:
    inputs:
      env:
        description: Target environment
        required: true
        default: staging
        type: choice
        options: [staging, production]
```

#### Other events

```yaml
on:
  release:
    types: [published]
  workflow_call: {}           # reusable workflow
  repository_dispatch:
    types: [deploy-command]
```
