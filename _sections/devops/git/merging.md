---
title: Merging
subtopic: git
group: Merging & Rebasing
order: 1
---

#### Merge a branch into current

Creates a merge commit that joins both histories.

```
git merge <branch>
```

<div class="mermaid">
gitGraph
  commit id: "A"
  commit id: "B"
  branch feature
  commit id: "C"
  commit id: "D"
  checkout main
  commit id: "E"
  merge feature id: "M (merge)"
</div>
