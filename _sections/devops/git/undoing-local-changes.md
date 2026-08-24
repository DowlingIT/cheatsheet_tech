---
title: Undoing Local Changes
subtopic: git
group: Undoing & Rewriting
order: 1
---

#### Discard unstaged changes to a file

```
git restore <file>
```

#### Discard all staged & unstaged changes to a file

```
git restore --staged --worktree <file>
```

#### Discard all unstaged changes

```
git restore .
```

#### Delete untracked files

Preview first with `-n`, then run with `-f`.

```
git clean -n
git clean -f
```
