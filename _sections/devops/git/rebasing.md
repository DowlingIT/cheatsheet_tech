---
title: Rebasing
subtopic: git
group: Merging & Rebasing
order: 3
---

#### Rebase current branch onto another

Replays your commits on top of the target, creating linear history. Rewrites commit hashes.

```
git switch feature
git rebase main
```

**Before** &mdash; branches have diverged:

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
</div>

**After** `git rebase main` &mdash; linear history:

<div class="mermaid">
%%{init: { 'gitGraph': {'showCommitLabel': true}} }%%
gitGraph
  commit id: "A"
  commit id: "B"
  commit id: "E"
  commit id: "C'"
  commit id: "D'"
</div>
