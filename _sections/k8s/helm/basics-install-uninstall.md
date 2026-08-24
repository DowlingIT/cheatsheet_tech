---
title: Install & Uninstall
subtopic: helm
group: Chart Basics
order: 2
---

#### Deploying a release

```bash
helm install myrelease ./mychart
helm install myrelease ./mychart -n staging --create-namespace
helm install myrelease repo/chart --version 1.2.3
helm uninstall myrelease
helm uninstall myrelease --keep-history    # release record stays for `helm history`
helm uninstall myrelease --dry-run           # preview what would be removed
```

A "release" is a named, installed instance of a chart in a cluster.
