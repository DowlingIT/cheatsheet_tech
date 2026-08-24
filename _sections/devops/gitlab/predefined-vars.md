---
title: Predefined Variables
subtopic: gitlab
group: Variables
order: 2
---

#### Common CI variables

```
$CI_COMMIT_SHA              # full commit SHA
$CI_COMMIT_SHORT_SHA        # 8-char SHA
$CI_COMMIT_BRANCH           # branch name
$CI_COMMIT_TAG              # tag name
$CI_COMMIT_MESSAGE          # commit message
$CI_PIPELINE_ID             # pipeline ID
$CI_PIPELINE_SOURCE         # push, merge_request_event, schedule, …
$CI_JOB_ID                  # job ID
$CI_JOB_NAME                # job name
$CI_STAGE_NAME              # stage name
$CI_PROJECT_PATH            # namespace/project
$CI_PROJECT_URL             # project web URL
$CI_REGISTRY                # container registry hostname
$CI_REGISTRY_IMAGE          # project container registry path
$CI_ENVIRONMENT_NAME        # deployment environment name
$CI_MERGE_REQUEST_IID       # MR number
```
