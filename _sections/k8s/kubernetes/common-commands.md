---
title: Common Commands
subtopic: kubernetes
group: kubectl Basics
order: 2
---

#### CRUD & inspect

```bash
kubectl get pods                          # list
kubectl get pods -o wide                    # more columns
kubectl get pods -o yaml                      # full manifest
kubectl describe pod my-pod                     # detailed info & events
kubectl apply -f deployment.yaml                  # create/update from a file
kubectl delete -f deployment.yaml                   # delete from a file
kubectl delete pod my-pod
```
