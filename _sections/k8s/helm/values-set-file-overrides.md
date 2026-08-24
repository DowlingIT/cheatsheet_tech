---
title: --set & -f Overrides
subtopic: helm
group: Values & Overrides
order: 2
---

#### Overriding at install/upgrade time

```bash
helm install myrelease ./mychart --set replicaCount=3
helm install myrelease ./mychart --set image.tag=2.0
helm install myrelease ./mychart -f values.staging.yaml
helm install myrelease ./mychart -f values.yaml -f values.staging.yaml
```

Later `-f` files and `--set` flags override earlier ones, left to right.
