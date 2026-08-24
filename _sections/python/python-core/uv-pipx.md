---
title: uv & pipx
subtopic: python-core
group: Packaging
order: 3
---

#### uv — fast project & env manager

```bash
uv init myapp            # new project
uv venv                  # create .venv
uv add django            # add + install a dependency
uv remove requests
uv sync                  # install from lockfile (uv.lock)
uv run pytest            # run a command in the project env
uv python install 3.13   # manage interpreters
```

#### pipx — install CLI apps in isolation

```bash
pipx install ruff        # each tool gets its own venv
pipx run black .         # run once, without installing
pipx list                pipx upgrade-all
pipx uninstall ruff
```
