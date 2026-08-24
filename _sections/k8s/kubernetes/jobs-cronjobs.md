---
title: Jobs & CronJobs
subtopic: kubernetes
group: Jobs & CronJobs
order: 1
---

#### Job & CronJob

```yaml
apiVersion: batch/v1
kind: Job
metadata:
  name: migrate
spec:
  template:
    spec:
      containers:
        - name: migrate
          image: my-app:latest
          command: ["./migrate"]
      restartPolicy: Never
---
apiVersion: batch/v1
kind: CronJob
metadata:
  name: nightly-cleanup
spec:
  schedule: "0 2 * * *"      # standard cron syntax
  jobTemplate:
    spec:
      template:
        spec:
          containers: [{ name: cleanup, image: my-app:latest }]
          restartPolicy: OnFailure
```
