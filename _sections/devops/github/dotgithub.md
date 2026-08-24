---
title: .github Folder
subtopic: github
group: Repository Files
order: 1
---

#### Common structure

```
.github/
  workflows/                → CI/CD workflow files
  CODEOWNERS                → auto-assign reviewers
  PULL_REQUEST_TEMPLATE.md
  ISSUE_TEMPLATE/
    bug_report.yml
    feature_request.yml
  dependabot.yml            → dependency update schedule
  funding.yml               → sponsor links
```

#### Dependabot config

```yaml
# .github/dependabot.yml
version: 2
updates:
  - package-ecosystem: npm
    directory: /
    schedule:
      interval: weekly
    open-pull-requests-limit: 5
    groups:
      dev-dependencies:
        patterns: ['*']
        dependency-type: development
```
