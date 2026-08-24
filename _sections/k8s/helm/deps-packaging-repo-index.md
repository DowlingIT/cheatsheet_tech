---
title: Packaging & Hosting a Repo
subtopic: helm
group: Dependencies & Packaging
order: 3
---

#### Package a chart, then publish it

```bash
helm package ./mychart                 # -> mychart-1.2.3.tgz
helm package ./mychart --sign --key ... --keyring ...   # optional provenance

helm repo index . --url https://example.com/charts   # (re)writes index.yaml
```

`index.yaml` is the whole repo: metadata for every packaged chart version.
Host it as static files (GitHub Pages, S3) — clients just need `repo add <url>`.

#### OCI registries skip the index entirely

```bash
helm push mychart-1.2.3.tgz oci://registry.example.com/charts
helm install myrelease oci://registry.example.com/charts/mychart --version 1.2.3
```
