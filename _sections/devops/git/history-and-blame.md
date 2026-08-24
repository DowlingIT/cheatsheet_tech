---
title: History & Blame
subtopic: git
group: Inspecting Changes
order: 3
---

#### Show commit history

```
git log --oneline
```

#### History with graph

```
git log --oneline --graph --all
```

#### Commits that modified a file

```
git log <file>
git log --follow <file>   # follow renames
```

#### Find commits that added or removed text

```
git log -G "pattern"
```

#### Who last changed each line

```
git blame <file>
```
