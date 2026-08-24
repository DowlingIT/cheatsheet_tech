---
title: Workflows
subtopic: git
group: Remote & Collaboration
order: 5
---

#### GitHub Flow (simple)

One long-lived branch. Features branch off, get reviewed via PR, merge back.

1. `git switch -c feature/thing` from `main`
2. Commit, push, open a pull request
3. Review, then merge PR into `main`
4. Deploy from `main`

#### GitFlow (structured releases)

`main` for production, `develop` for integration.

- `feature/*` &rarr; branches off & merges to `develop`
- `release/*` &rarr; branches off `develop`, merges to `main` + `develop`
- `hotfix/*` &rarr; branches off `main`, merges to `main` + `develop`

#### Trunk-based development

Everyone commits to `main` (or short-lived branches merged within a day). Relies on feature flags and CI.
