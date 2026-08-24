---
title: Install & Run
subtopic: fastapi
group: Terminology & Structure
order: 3
---

#### Setup

```bash
pip install "fastapi[standard]"
fastapi dev main.py         # auto-reload dev server
fastapi run main.py         # production-style run
# or:
uvicorn main:app --reload
```

Interactive docs auto-generated at `/docs` (Swagger UI) and `/redoc`.
