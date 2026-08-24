---
title: Key Concepts
subtopic: github
group: Workflows
order: 0
---

#### Automation model

**Workflow** — a YAML file in `.github/workflows/`; triggered by events and composed of jobs.

**Job** — a group of steps that run sequentially on the same runner. Jobs run in parallel by default; use `needs:` to sequence them.

**Step** — a single task inside a job: either a shell command (`run:`) or a reusable action (`uses:`).

**Action** — a packaged, reusable step pulled from the Marketplace or a repo (`uses: actions/checkout@v4`).

#### Infrastructure

**Runner** — the VM or container that executes a job. GitHub provides hosted runners (Ubuntu, Windows, macOS); you can also register self-hosted runners.

**Event** — what triggers a workflow: `push`, `pull_request`, `schedule`, `workflow_dispatch`, etc.

#### Configuration

**Context** — runtime objects injected into expressions: `github`, `env`, `secrets`, `vars`, `steps`, `job`, `runner`.

**Environment** — a named deployment target (staging, production) with its own secrets, variables, and protection rules (required reviewers, wait timers).

**Secret / Variable** — secrets are encrypted and masked in logs; variables (`vars`) are plain-text and visible in logs.

**Artifact** — files uploaded by one job and downloaded by another, or retained after the run for inspection.
