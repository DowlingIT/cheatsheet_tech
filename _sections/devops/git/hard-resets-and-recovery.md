---
title: Hard Resets & Recovery
subtopic: git
group: Undoing & Rewriting
order: 5
---

#### Undo last commit, discard changes

```
git reset --hard HEAD~1
```

#### Restore a file from another commit

```
git restore <file> --source <commit>
```

#### Recover lost commits

`reflog` shows everywhere HEAD has pointed.

```
git reflog
git reset --hard <commit>
```
