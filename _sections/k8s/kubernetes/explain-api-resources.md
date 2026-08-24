---
title: Discovering the API
subtopic: kubernetes
group: kubectl Basics
order: 5
---

#### Look up fields & resource types without leaving the terminal

```bash
kubectl explain pod.spec.containers            # field docs for any object
kubectl explain deployment.spec.strategy --recursive

kubectl api-resources                           # every kind + short name + namespaced?
kubectl api-resources --namespaced=false
kubectl api-versions                              # apiVersion strings available
```
