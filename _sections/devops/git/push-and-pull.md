---
title: Push & Pull
subtopic: git
group: Remote & Collaboration
order: 1
---

#### Push to remote

```
git push origin main
```

#### Push & set upstream tracking

Links local branch to remote so future `push`/`pull` work without arguments.

```
git push -u origin <branch>
```

#### Force push (safe)

Fails if someone else pushed first.

```
git push --force-with-lease
```

#### Pull (fetch + merge) / with rebase

```
git pull
git pull --rebase
```
