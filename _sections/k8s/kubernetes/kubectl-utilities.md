---
title: cp, proxy, wait & diff
subtopic: kubernetes
group: kubectl Basics
order: 4
---

#### Files, tunnels & sync

```bash
kubectl cp my-pod:/var/log/app.log ./app.log      # pod -> local
kubectl cp ./config.json my-pod:/etc/config.json  # local -> pod

kubectl port-forward pod/my-pod 8080:80           # also: svc/, deploy/
kubectl proxy --port=8001                          # local proxy to the API server
```

#### Waiting & previewing changes

```bash
kubectl wait --for=condition=Ready pod/my-pod --timeout=60s
kubectl wait --for=delete pod/my-pod --timeout=30s

kubectl diff -f deployment.yaml    # show what apply would change
```
