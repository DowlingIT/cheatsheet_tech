---
title: Revert Options
subtopic: git
group: Undoing & Rewriting
order: 3
---

#### Revert without auto-committing

```
git revert --no-commit <commit>
```

#### Revert a merge commit

`-m 1` keeps the first parent (the branch you merged into).

```
git revert -m 1 <merge-commit>
```

#### Revert a range of commits

```
git revert <oldest>^..<newest>
```
