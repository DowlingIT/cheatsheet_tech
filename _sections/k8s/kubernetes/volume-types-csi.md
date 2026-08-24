---
title: Volume Types & CSI
subtopic: kubernetes
group: Storage
order: 3
---

#### Common in-pod volume types

```yaml
volumes:
  - name: scratch
    emptyDir: {}                 # ephemeral, deleted with the pod
  - name: host-logs
    hostPath: { path: /var/log }  # node's filesystem — use sparingly
  - name: cfg
    configMap: { name: app-config }
  - name: data
    persistentVolumeClaim: { claimName: data-pvc }
```

#### CSI — Container Storage Interface

```
Standard plugin API so any storage vendor (EBS, Azure Disk, Ceph, Portworx...)
can provide PVs without k8s core code knowing about it. A CSI driver runs as
a DaemonSet (node plugin) + Deployment/StatefulSet (controller plugin) and is
what a StorageClass's `provisioner:` field points to.
```
