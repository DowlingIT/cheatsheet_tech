---
title: Job Patterns
subtopic: kubernetes
group: Jobs & CronJobs
order: 2
---

#### Parallelism, retries & cleanup

```yaml
apiVersion: batch/v1
kind: Job
metadata:
  name: batch-work
spec:
  completions: 5              # total successful pods needed
  parallelism: 2               # how many run at once
  backoffLimit: 4                # retries before marking failed
  activeDeadlineSeconds: 300       # kill the whole job after this long
  ttlSecondsAfterFinished: 3600     # auto-delete after completion
  template:
    spec:
      containers: [{ name: work, image: my-app:latest }]
      restartPolicy: Never
```
