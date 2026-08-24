---
title: templates/ Files
subtopic: helm
group: Chart Templates
order: 1
render_with_liquid: false
---

#### Templated manifests

```yaml
# templates/deployment.yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: {{ .Release.Name }}-app
spec:
  replicas: {{ .Values.replicaCount }}
  template:
    spec:
      containers:
        - name: app
          image: "{{ .Values.image.repository }}:{{ .Values.image.tag }}"
```

Every file under `templates/` is rendered through Go templates before being applied.
