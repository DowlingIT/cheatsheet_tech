---
title: Artifacts
subtopic: github
group: Artifacts & Cache
order: 1
---

#### Upload

```yaml
- uses: actions/upload-artifact@v4
  with:
    name: build-output
    path: dist/
    retention-days: 7
    if-no-files-found: error
```

#### Download in the same workflow

```yaml
- uses: actions/download-artifact@v4
  with:
    name: build-output
    path: dist/
```

#### Download from another workflow

```yaml
- uses: dawidd6/action-download-artifact@v6
  with:
    workflow: build.yml
    name: build-output
    path: dist/
```
