---
title: Cherry-Pick
subtopic: git
group: Cherry-Pick & Conflicts
order: 1
---

#### Cherry-pick a commit

Copies a single commit onto the current branch.

```
git cherry-pick <commit>
```

<div class="mermaid">
%%{init: { 'gitGraph': {'showCommitLabel': true}} }%%
gitGraph
  commit id: "A"
  commit id: "B"
  branch feature
  commit id: "C"
  commit id: "D"
  checkout main
  commit id: "E"
  cherry-pick id: "D"
</div>
