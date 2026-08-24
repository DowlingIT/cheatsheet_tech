---
title: Ranges & Combining
subtopic: git
group: Branching & References
order: 4
---

#### Combine refs

```
HEAD~2^2  # back 2, then second parent
```

#### Ranges

```
git log main..feature    # in feature, not main
git log main...feature   # in either, not both
```

<div class="mermaid">
%%{init: { 'gitGraph': {'showCommitLabel': true}} }%%
gitGraph
  commit id: "HEAD~3"
  commit id: "HEAD~2"
  commit id: "HEAD~1 (HEAD^)"
  commit id: "HEAD"
</div>
