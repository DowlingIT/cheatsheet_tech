---
title: Remote Branches
subtopic: git
group: Remote & Collaboration
order: 4
---

#### See which branch tracks which remote

```
git branch -vv
```

#### Set upstream for existing branch

```
git branch -u origin/<branch>
```

#### List / check out remote branches

```
git branch -r
git switch <remote-branch>
```

#### Delete a remote branch

```
git push origin --delete <branch>
```
