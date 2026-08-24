---
title: Runners
subtopic: gitlab
group: Runners & Repo
order: 1
---

#### Runner types

- **Shared runners** — provided by GitLab.com, available to all projects
- **Group runners** — registered to a GitLab group
- **Project runners** — registered to a specific project

#### Targeting runners with tags

```yaml
my-job:
  tags:
    - docker
    - linux
    - production
  script: [./deploy.sh]
```

#### Register a runner

```bash
gitlab-runner register \
  --url https://gitlab.com \
  --token $RUNNER_TOKEN \
  --executor docker \
  --docker-image alpine:latest
```

#### Runner config snippet (`config.toml`)

```toml
[[runners]]
  name = "my-runner"
  executor = "docker"
  [runners.docker]
    image = "alpine:latest"
    privileged = false
    volumes = ["/cache"]
```
