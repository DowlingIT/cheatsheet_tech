---
title: Amending & Undoing
subtopic: git
group: Undoing & Rewriting
order: 4
---

#### Amend last commit message

```
git commit --amend -m "new message"
```

#### Add forgotten files to last commit

```
git add <file>
git commit --amend --no-edit
```

#### Undo last commit, keep changes staged

```
git reset --soft HEAD~1
```

#### Undo last commit, keep changes unstaged

```
git reset HEAD~1
```
