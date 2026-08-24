---
title: Hooks
subtopic: helm
group: Chart Templates
order: 5
render_with_liquid: false
---

#### Run extra manifests at specific lifecycle points

```yaml
# templates/migrate-job.yaml
apiVersion: batch/v1
kind: Job
metadata:
  name: {{ .Release.Name }}-migrate
  annotations:
    "helm.sh/hook": pre-upgrade,pre-install
    "helm.sh/hook-weight": "0"                 # lower runs first
    "helm.sh/hook-delete-policy": hook-succeeded
spec:
  template:
    spec:
      containers: [{ name: migrate, image: my-app:latest, command: ["./migrate"] }]
      restartPolicy: Never
```

```
pre-install / post-install       around the first install
pre-upgrade / post-upgrade         around every upgrade
pre-delete / post-delete             around uninstall
pre-rollback / post-rollback           around rollback
```
