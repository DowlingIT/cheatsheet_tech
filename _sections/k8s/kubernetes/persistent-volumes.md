---
title: PersistentVolumes & Claims
subtopic: kubernetes
group: Storage
order: 1
---

#### PVC & using it in a pod

```yaml
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: data-pvc
spec:
  accessModes: [ReadWriteOnce]
  resources:
    requests:
      storage: 10Gi
```

```yaml
volumes:
  - name: data
    persistentVolumeClaim:
      claimName: data-pvc
```

#### Access modes

```
ReadWriteOnce (RWO)   mounted read-write by a single node
ReadOnlyMany (ROX)    mounted read-only by many nodes
ReadWriteMany (RWX)   mounted read-write by many nodes — needs NFS/CSI support
ReadWriteOncePod       mounted read-write by a single pod (k8s 1.29+)
```
