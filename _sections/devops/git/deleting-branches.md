---
title: Deleting Branches
subtopic: git
group: Branching & References
order: 2
---

#### Delete a branch (safe)

Fails if the branch has unmerged changes.

```
git branch -d <name>
```

#### Delete a branch (force)

```
git branch -D <name>
```

#### Check out a specific commit

Creates a detached HEAD — you're not on any branch.

```
git checkout <commit>
```

To start a branch from that point:

```
git switch -c <name> <commit>
```
