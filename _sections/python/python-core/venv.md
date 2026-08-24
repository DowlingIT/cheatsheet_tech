---
title: Virtual Environments
subtopic: python-core
group: Packaging
order: 1
---

#### Create & activate

```bash
python -m venv .venv

# Activate
source .venv/bin/activate       # Linux / macOS
.venv\Scripts\activate          # Windows

deactivate
```

#### pip

```bash
pip install requests
pip install "django>=4.2,<5"
pip install -r requirements.txt
pip install -e .                  # editable / dev install
pip freeze > requirements.txt
pip list --outdated
pip show django                   # package info
pip uninstall package
```
