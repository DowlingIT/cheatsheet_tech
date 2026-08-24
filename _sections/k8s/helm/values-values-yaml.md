---
title: values.yaml
subtopic: helm
group: Values & Overrides
order: 1
---

#### Default configuration

```yaml
replicaCount: 2
image:
  repository: myapp
  tag: "1.0"
ingress:
  enabled: false
resources: {}
```

Every value read via `.Values.*` in a template must have a corresponding
key here (or be supplied at install time).
