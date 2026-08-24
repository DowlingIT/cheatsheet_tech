---
title: pyproject.toml
subtopic: python-core
group: Packaging
order: 2
---

#### Modern project setup

```toml
[build-system]
requires = ["hatchling"]
build-backend = "hatchling.build"

[project]
name = "my-app"
version = "0.1.0"
requires-python = ">=3.11"
dependencies = [
    "django>=4.2",
    "requests>=2.31",
]

[project.optional-dependencies]
dev = ["pytest", "ruff", "mypy"]

[tool.ruff.lint]
select = ["E", "F", "I"]

[tool.mypy]
strict = true
```

#### Common tooling

```bash
python -m build         # build sdist + wheel
uv venv && uv pip install django   # fast uv workflow
uv run python manage.py runserver  # run via uv
```
