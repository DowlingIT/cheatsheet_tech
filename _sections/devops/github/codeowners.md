---
title: CODEOWNERS
subtopic: github
group: Repository Files
order: 2
---

#### Format

```
# .github/CODEOWNERS

# Default: all files
*                   @org/team-name

# Specific paths
/src/api/           @alice @bob
*.ts                @org/frontend-team
docs/               @org/docs-team
```

#### How it works

- Last matching rule wins
- Matched owners are auto-added as required reviewers on PRs
- Requires branch protection rule: **Require review from Code Owners**
- Works with GitHub Teams (`@org/team`) or individual users (`@username`)
