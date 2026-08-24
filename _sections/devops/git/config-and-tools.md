---
title: Config & Tools
subtopic: git
group: Reference
order: 3
---

#### Set your diff/merge tool

```
git config --global diff.tool vscode
git config --global merge.tool vscode
```

#### Create aliases

```
git config --global alias.st status
git config --global alias.co checkout
git config --global alias.br branch
```

#### Important files

- `.git/config` &mdash; local repo config
- `~/.gitconfig` &mdash; global user config
- `.gitignore` &mdash; files to exclude from tracking
