---
title: Context & Config
subtopic: kubernetes
group: kubectl Basics
order: 1
---

#### kubeconfig & contexts

```bash
kubectl config get-contexts
kubectl config current-context
kubectl config use-context my-cluster
kubectl config set-context --current --namespace=my-ns

kubectl get namespaces
kubectl get pods -n my-ns
kubectl get pods --all-namespaces
```
