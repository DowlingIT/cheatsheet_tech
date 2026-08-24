---
title: Predefined Env Vars
subtopic: github
group: Secrets & Variables
order: 4
---

#### Git & commit

```
$GITHUB_SHA                 # full commit SHA
$GITHUB_REF                 # refs/heads/main or refs/tags/v1.0
$GITHUB_REF_NAME            # branch or tag name (short)
$GITHUB_HEAD_REF            # PR source branch
$GITHUB_BASE_REF            # PR target branch
```

#### Run context

```
$GITHUB_WORKFLOW            # workflow name
$GITHUB_JOB                 # job name
$GITHUB_RUN_ID              # unique run ID
$GITHUB_RUN_NUMBER          # sequential run counter
$GITHUB_EVENT_NAME          # push, pull_request, etc.
$GITHUB_ACTOR               # triggering username
$GITHUB_REPOSITORY          # owner/repo
$GITHUB_WORKSPACE           # checkout directory path
```

#### Special files (append to activate)

```bash
echo "KEY=value"  >> $GITHUB_ENV        # set env for next steps
echo "key=value"  >> $GITHUB_OUTPUT     # set step output
echo "# Heading"  >> $GITHUB_STEP_SUMMARY  # job summary markdown
```
