---
title: Fast-Forward & Squash
subtopic: git
group: Merging & Rebasing
order: 2
---

#### Fast-forward merge

When main has no new commits, the pointer moves forward. No merge commit needed.

<div class="mermaid">
gitGraph
  commit id: "A"
  commit id: "B"
  branch feature
  commit id: "C"
  commit id: "D"
  checkout main
  merge feature id: " " tag: "main fast-forwards"
</div>

#### Squash merge

Combines all branch commits into one on the target.

```
git merge --squash <branch>
git commit -m "message"
```
