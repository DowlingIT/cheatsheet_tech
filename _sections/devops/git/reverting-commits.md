---
title: Reverting Commits
subtopic: git
group: Undoing & Rewriting
order: 2
---

#### Revert a commit

Creates a new undo commit. Safe for shared branches &mdash; doesn't rewrite history.

```
git revert <commit>
```

**Before** &mdash; C introduced a bug:

<div class="mermaid">
%%{init: { 'gitGraph': {'showCommitLabel': true}} }%%
gitGraph
  commit id: "A"
  commit id: "B"
  commit id: "C" type: REVERSE
</div>

**After** `git revert C` &mdash; bug undone, history preserved:

<div class="mermaid">
%%{init: { 'gitGraph': {'showCommitLabel': true}} }%%
gitGraph
  commit id: "A"
  commit id: "B"
  commit id: "C" type: REVERSE
  commit id: "Revert C"
</div>
