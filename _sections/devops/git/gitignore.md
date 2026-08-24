---
title: Gitignore
subtopic: git
group: Reference
order: 2
---

#### Pattern syntax

```
*.log          # any .log file
build/         # directory named build
/TODO          # only root TODO, not sub/TODO
!important.log # negate: do track this file
**/debug       # match in any subdirectory
```

#### Remove a tracked file from the repo

```
git rm --cached <file>
```

File stays on disk but leaves version control. Commit afterward.

#### Check what rule is ignoring a file

```
git check-ignore -v <file>
```
