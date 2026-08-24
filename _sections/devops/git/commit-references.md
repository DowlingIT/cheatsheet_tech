---
title: Commit References
subtopic: git
group: Branching & References
order: 3
---

#### By name, tag, or hash

`main`, `feature/login`, `v1.0`, `3e887ab`, `origin/main`

#### HEAD &mdash; current commit

```
HEAD
```

#### ~ walks back linearly

```
HEAD~1    # one commit back
HEAD~3    # three commits back
```

#### ^ picks a parent (for merges)

```
HEAD^     # first parent (same as HEAD~1)
HEAD^2    # second parent of a merge
```
