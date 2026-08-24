---
title: Committing
subtopic: git
group: Basics
order: 3
---

#### Commit staged changes

```
git commit -m "message"
```

#### Stage & commit all tracked files

Skips `git add` for files Git already tracks. Does not add new untracked files.

```
git commit -am "message"
```

#### Move, rename, or delete

```
git mv <old> <new>
git rm <file>
git rm --cached <file>
```

`--cached` untracks without deleting the file.
