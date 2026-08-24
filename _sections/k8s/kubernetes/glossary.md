---
title: Glossary
subtopic: kubernetes
group: Terminology & Style
order: 1
---

#### Core objects

```
Pod            smallest deployable unit — one or more containers sharing network/storage
Node           a worker machine (VM or physical) that runs pods
Cluster        a set of nodes managed together, with a control plane
Namespace      virtual cluster for scoping resources within a cluster
ReplicaSet     ensures a specified number of pod replicas are running
Deployment     manages ReplicaSets, enables rolling updates & rollbacks
Service        stable network endpoint that routes to a set of pods
```

#### Control plane

```
kube-apiserver     front door — all kubectl commands talk to this
etcd                 key-value store holding all cluster state
kube-scheduler          assigns pods to nodes
kube-controller-manager   runs controllers (ReplicaSet, Node, etc.)
kubelet                     agent on each node that runs pods
kube-proxy                    maintains network rules on each node
```
