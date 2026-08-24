---
title: Settings Files
subtopic: vscode
group: Settings
order: 1
---

#### Scope & location

```
User settings     applies everywhere
                  ~/.config/Code/User/settings.json (Linux/Mac)
                  %APPDATA%\Code\User\settings.json (Windows)

Workspace         overrides user, applies to this project
                  .vscode/settings.json
```

User settings open in UI via `Ctrl+,`; add `--json` flag or use `Ctrl+Shift+P → Open User Settings (JSON)` to edit raw JSON.

#### Other `.vscode/` files

```
launch.json       debug configurations (F5)
tasks.json        task runner definitions (Ctrl+Shift+B)
extensions.json   recommended extensions for this project
```
