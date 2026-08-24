---
title: Search & List
subtopic: helm
group: Repositories & Releases
order: 2
---

#### Finding charts & releases

```bash
helm search repo postgres          # search added repos
helm search hub wordpress            # search Artifact Hub
helm list                              # releases in current namespace
helm list -A                             # releases across all namespaces
```
