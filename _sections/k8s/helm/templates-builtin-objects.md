---
title: Built-in Objects
subtopic: helm
group: Chart Templates
order: 2
---

#### Available inside templates

```
.Values          merged values.yaml + --set/-f overrides
.Release.Name       the release name
.Release.Namespace    the target namespace
.Chart.Name             chart name from Chart.yaml
.Chart.Version            chart version from Chart.yaml
.Files                      access to non-template files in the chart
```
