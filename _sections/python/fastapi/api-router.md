---
title: APIRouter
subtopic: fastapi
group: Routing & Path Operations
order: 3
---

#### Modular routes

```python
# routers/users.py
from fastapi import APIRouter

router = APIRouter(prefix="/users", tags=["users"])

@router.get("/")
async def list_users():
    ...

@router.get("/{user_id}")
async def get_user(user_id: int):
    ...
```

```python
# main.py
app.include_router(users.router)
```
