---
title: Umbrella Charts
subtopic: helm
group: Dependencies & Packaging
order: 2
---

#### One parent chart composing several sub-charts

```
myapp/
  Chart.yaml            # dependencies: [api, worker, postgresql]
  values.yaml              # api: {...}  worker: {...}  postgresql: {...}
  charts/
    api/
    worker/
```

```yaml
# parent values.yaml — keys match each dependency's alias/name
global:
  imageRegistry: registry.example.com   # visible to every sub-chart as .Values.global.*
api:
  replicaCount: 2
postgresql:
  enabled: true
```

`global` values and `condition`/`tags` in `Chart.yaml` are how a parent chart
configures and toggles its children — one `helm install` deploys the whole app.
