---
title: Imperative Jobs & Manual Triggers
subtopic: kubernetes
group: Jobs & CronJobs
order: 3
---

#### Creating & inspecting

```bash
kubectl create job migrate --image=my-app:latest -- ./migrate
kubectl create cronjob nightly --image=my-app:latest \
  --schedule="0 2 * * *" -- ./cleanup

kubectl get jobs
kubectl get cronjobs
```

#### Running a CronJob's job right now

```bash
kubectl create job manual-run --from=cronjob/nightly
```
