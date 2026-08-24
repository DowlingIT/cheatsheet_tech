---
title: PR & Issue Templates
subtopic: github
group: Repository Files
order: 3
---

#### PR template

```markdown
<!-- .github/PULL_REQUEST_TEMPLATE.md -->
## What changed

## Why

## Testing done

## Checklist
- [ ] Tests added or updated
- [ ] Docs updated
```

#### Issue template (YAML form)

```yaml
# .github/ISSUE_TEMPLATE/bug_report.yml
name: Bug Report
description: File a bug report
labels: [bug]
body:
  - type: textarea
    id: description
    attributes:
      label: Describe the bug
    validations:
      required: true
  - type: dropdown
    id: severity
    attributes:
      label: Severity
      options: [Low, Medium, High, Critical]
```
