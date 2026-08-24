---
title: Resolving Conflicts
subtopic: git
group: Cherry-Pick & Conflicts
order: 3
---

#### When do conflicts happen?

When two branches change the same lines, or one deletes a file the other modified.

#### Conflict markers

```
<<<<<<< HEAD
your changes
=======
their changes
>>>>>>> feature-branch
```

Edit the file to keep the correct code, then remove all markers.
