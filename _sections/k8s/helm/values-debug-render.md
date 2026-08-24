---
title: Debug & Render
subtopic: helm
group: Values & Overrides
order: 3
---

#### Checking output before applying

```bash
helm template myrelease ./mychart          # render manifests locally
helm install myrelease ./mychart --dry-run   # simulate against the cluster
helm lint ./mychart                            # check chart for issues
helm get values myrelease                        # values used by a release
```
