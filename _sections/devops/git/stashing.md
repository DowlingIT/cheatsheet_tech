---
title: Stashing
subtopic: git
group: Basics
order: 4
---

#### Stash changes

Saves uncommitted changes and reverts the working directory. Useful for switching branches without committing.

```
git stash
```

#### List stashes

```
git stash list
```

#### Restore & delete most recent stash

```
git stash pop
```

#### Restore but keep the stash

```
git stash apply
```

#### Drop a specific stash

```
git stash drop stash@{n}
```
