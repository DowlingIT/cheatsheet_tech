---
title: Project Structure
subtopic: fastapi
group: Terminology & Structure
order: 2
---

#### Typical layout

```
app/
├── main.py            # creates FastAPI(), includes routers
├── routers/
│   ├── users.py
│   └── items.py
├── models.py           # SQLAlchemy models
├── schemas.py           # Pydantic models
├── crud.py                # DB access functions
├── dependencies.py          # shared Depends() callables
├── database.py                # engine + SessionLocal
└── config.py                    # Settings (BaseSettings)
```

```python
# main.py
from fastapi import FastAPI
from .routers import users, items

app = FastAPI(title="My API")
app.include_router(users.router)
app.include_router(items.router)
```
