---
title: After Resolving
subtopic: git
group: Cherry-Pick & Conflicts
order: 4
---

#### Stage & continue

```
git add <file>
git merge --continue
git rebase --continue
git cherry-pick --continue
```

#### Abort & go back

```
git merge --abort
git rebase --abort
git cherry-pick --abort
```

#### Accept all of theirs or ours

```
git checkout --theirs <file> && git add <file>
git checkout --ours <file> && git add <file>
```
