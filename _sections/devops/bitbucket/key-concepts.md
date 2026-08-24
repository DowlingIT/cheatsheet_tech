---
title: Key Concepts
subtopic: bitbucket
group: Pipelines
order: 0
---

#### Automation model

**Pipeline** — the full automation config defined in `bitbucket-pipelines.yml` at the repo root.

**Step** — the fundamental unit of work; each step runs in its own fresh Docker container. Steps within a pipeline run sequentially unless wrapped in `parallel:`.

**Stage** — a named group of parallel steps, used to add a label to a logical phase (`- stage: Deploy`).

#### Data & dependencies

**Cache** — directories persisted across pipeline runs to avoid re-downloading dependencies (npm, pip, Maven, etc.).

**Artifact** — files produced by one step and made available to all later steps in the same pipeline run. Unlike caches, artifacts are not shared across runs.

**Service** — a sidecar container (Postgres, Redis, Docker daemon) that runs alongside a step and is torn down when the step finishes.

#### Configuration

**Workspace** — the Bitbucket account or team that owns repositories; the top level above projects and repos.

**Deployment** — a step tagged with `deployment: test|staging|production`, linking it to an environment bucket in the UI for tracking history and scoping variables.

**Custom pipeline** — a pipeline defined under `custom:` that must be triggered manually from the UI or API, not by a push or PR.

**Variable scope** — variables cascade from workspace → repository → deployment environment, with each level able to override the one above.
