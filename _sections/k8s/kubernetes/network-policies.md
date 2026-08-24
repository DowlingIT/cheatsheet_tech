---
title: NetworkPolicy
subtopic: kubernetes
group: Networking
order: 3
---

#### Deny-by-default, allow specific traffic

```yaml
apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  name: allow-from-frontend
spec:
  podSelector:
    matchLabels: { app: api }        # applies to pods with this label
  policyTypes: [Ingress]
  ingress:
    - from:
        - podSelector:
            matchLabels: { app: frontend }
      ports:
        - port: 8080
```

```
Requires a CNI plugin that enforces policies (Calico, Cilium, ...) —
Flannel alone does not. No policies for a pod = all traffic allowed.
```
