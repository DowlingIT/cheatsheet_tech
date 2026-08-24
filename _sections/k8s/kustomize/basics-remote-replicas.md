---
title: Remote Bases & Replica Count
subtopic: kustomize
group: Kustomization Basics
order: 4
---

#### Referencing a base straight from Git

```yaml
resources:
  - github.com/org/repo/base?ref=v1.2.3   # tag, branch, or commit SHA
  - ../../local-base                       # local paths still work the same way
```

No clone step needed — `kustomize build`/`kubectl apply -k` fetch it directly.

#### Setting replica count without a patch

```yaml
replicas:
  - name: my-app
    count: 5
```
