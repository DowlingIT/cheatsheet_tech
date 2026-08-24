---
title: Create & Structure
subtopic: helm
group: Chart Basics
order: 1
---

#### Scaffolding a chart

```bash
helm create mychart
```

```
mychart/
  Chart.yaml          name, version, metadata
  values.yaml          default configuration values
  templates/             Kubernetes manifests (templated)
  charts/                   bundled sub-charts (dependencies)
```
