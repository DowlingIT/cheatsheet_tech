---
title: Repository Settings
subtopic: bitbucket
group: Config
order: 1
---

#### Branch permissions

Set in **Repository Settings → Branch restrictions**:
- Restrict who can push or merge
- Require minimum number of approvals
- Require passing builds before merge
- Prevent history rewrites (force push / delete)

#### Merge checks

Set in **Repository Settings → Merge checks**:
- Minimum approvals required
- No unresolved tasks/comments
- Minimum successful builds

#### SSH keys for pipelines

Add external host fingerprints in **Repository Settings → SSH Keys → Known hosts** to allow cloning private repos inside pipelines without prompt failures.

#### .bitbucket folder

Not currently used by Bitbucket itself, but a common convention for storing internal scripts and config used by `bitbucket-pipelines.yml`:

```
.bitbucket/
  scripts/
    deploy.sh
    notify.sh
```
