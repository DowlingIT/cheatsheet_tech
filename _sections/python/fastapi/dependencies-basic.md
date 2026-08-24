---
title: Basic Dependencies
subtopic: fastapi
group: Dependency Injection
order: 1
---

#### Depends()

```python
from fastapi import Depends
from typing import Annotated

async def common_params(q: str | None = None, skip: int = 0, limit: int = 10):
    return {"q": q, "skip": skip, "limit": limit}

@app.get("/items")
async def list_items(commons: Annotated[dict, Depends(common_params)]):
    return commons

# app-wide, applied to every route on the app/router:
app = FastAPI(dependencies=[Depends(verify_token)])
```
