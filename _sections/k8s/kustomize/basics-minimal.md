---
title: Minimal kustomization.yaml
subtopic: kustomize
group: Kustomization Basics
order: 1
---

#### Declaring resources

```yaml
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

resources:
  - deployment.yaml
  - service.yaml
```

`kustomize` composes plain, unmodified YAML — no templating language involved.
