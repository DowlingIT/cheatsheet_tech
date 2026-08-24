---
title: Interactive Rebase
subtopic: git
group: Merging & Rebasing
order: 4
---

#### Interactive rebase (last N commits)

Squash, reorder, edit, or drop commits.

```
git rebase -i HEAD~<n>
```

Verbs: `pick` keep, `squash` meld into previous, `fixup` meld & discard message, `reword` change message, `edit` pause to amend, `drop` remove.

#### After rebase, force push to update remote

```
git push --force-with-lease
```
