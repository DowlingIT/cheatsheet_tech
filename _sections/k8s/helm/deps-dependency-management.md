---
title: Dependencies
subtopic: helm
group: Dependencies & Packaging
order: 1
---

#### Declaring & pulling sub-charts

```yaml
# Chart.yaml
dependencies:
  - name: postgresql
    version: "13.x"
    repository: https://charts.bitnami.com/bitnami
    condition: postgresql.enabled   # toggled from values.yaml
```

```bash
helm dependency update ./mychart   # fetch into charts/*.tgz, writes Chart.lock
helm dependency build ./mychart      # re-fetch from the existing Chart.lock
helm dependency list ./mychart         # show status: ok / missing
```

Commit `Chart.lock` (and usually `charts/*.tgz`) — this is chart vendoring,
pinning dependency versions instead of re-resolving them on every install.
