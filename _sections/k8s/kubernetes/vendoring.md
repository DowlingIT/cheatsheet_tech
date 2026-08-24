---
title: What "Vendoring" Means Here
subtopic: kubernetes
group: Extending Kubernetes
order: 2
---

#### Copying a dependency into your own repo, pinned, instead of fetching it live

```
Helm chart deps    helm dependency update pulls charts into charts/*.tgz —
                    commit them so `helm install` works with no network/registry access
CRD manifests       check a third-party operator's CRD YAML into your repo at a
                    known version rather than `kubectl apply -f <url>` at deploy time
Base images         pin a digest (image@sha256:...) instead of a floating tag
```

```
Trade-off: vendoring trades "always latest" for reproducible, auditable,
offline-capable builds — the standard practice for anything hitting prod.
```
