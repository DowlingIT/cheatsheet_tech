---
title: Key Concepts
subtopic: gitlab
group: Pipeline Basics
order: 0
---

#### Automation model

**Pipeline** — the full CI/CD run, composed of stages and jobs, defined in `.gitlab-ci.yml`.

**Stage** — a phase of the pipeline. All jobs in the same stage run in parallel; stages run sequentially. Declare order under the top-level `stages:` key.

**Job** — the fundamental unit: a named block with a `script:` that runs on a runner. Jobs in different stages can be linked with `needs:` to bypass stage ordering.

**DAG (Directed Acyclic Graph)** — when you use `needs:`, GitLab skips stage-based sequencing and runs jobs as soon as their dependencies finish, reducing total pipeline time.

#### Infrastructure

**Runner** — an agent process that picks up jobs from GitLab. Can be shared (GitLab.com), group-scoped, or project-specific. Executors include Docker, Shell, and Kubernetes.

**Executor** — how the runner launches jobs: `docker` (isolated container per job), `shell` (runs directly on the host), `kubernetes` (spins up a pod).

#### Data & configuration

**Artifact** — files a job produces and optionally passes to downstream jobs or stores for download. GitLab also parses special report artifacts (JUnit, coverage, dotenv).

**Cache** — directories persisted between pipeline runs (not between jobs in the same run — use artifacts for that).

**Environment** — a named deployment target tracked in the GitLab UI with deployment history, rollback, and optional stop actions.

**Protected branch/tag** — restricts who can push and which CI/CD variables and runners are available, preventing untrusted code from accessing production secrets.
