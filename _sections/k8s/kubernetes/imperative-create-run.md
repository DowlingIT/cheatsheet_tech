---
title: Imperative Create & Run
subtopic: kubernetes
group: kubectl Basics
order: 3
---

#### Generate objects without a YAML file

```bash
kubectl run my-pod --image=nginx:1.25 --restart=Never    # single pod
kubectl create deployment my-app --image=nginx:1.25 --replicas=3
kubectl create job migrate --image=my-app:latest -- ./migrate
kubectl expose deployment my-app --port=80 --target-port=8080
```

#### Print the YAML instead of applying it

```bash
kubectl create deployment my-app --image=nginx:1.25 \
  --dry-run=client -o yaml > deployment.yaml
```

```
--dry-run=client   don't send to the API server, just render
--dry-run=server   validate against the API server, still don't persist
```
