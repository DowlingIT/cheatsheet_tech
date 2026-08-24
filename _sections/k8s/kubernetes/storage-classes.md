---
title: StorageClasses & Dynamic Provisioning
subtopic: kubernetes
group: Storage
order: 2
---

#### No PV needed — the provisioner creates one on demand

```yaml
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: fast
provisioner: ebs.csi.aws.com     # CSI driver name
parameters:
  type: gp3
reclaimPolicy: Delete             # or Retain — what happens to the PV on PVC delete
volumeBindingMode: WaitForFirstConsumer  # delay binding until a pod is scheduled
```

```yaml
spec:
  storageClassName: fast    # PVC requests this class instead of a pre-made PV
  accessModes: [ReadWriteOnce]
  resources: { requests: { storage: 10Gi } }
```

```bash
kubectl get storageclass    # one is usually marked (default)
```
