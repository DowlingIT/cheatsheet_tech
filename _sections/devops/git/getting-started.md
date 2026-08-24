---
title: Getting Started
subtopic: git
group: Basics
order: 1
---

#### Set your name & email

```
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Without `--global`, the setting applies only to the current repo.

#### Initialize a new repo

```
git init
```

#### Clone an existing repo

```
git clone <url>
git clone <url> <directory>
```

#### Set default branch name

```
git config --global init.defaultBranch main
```
