---
title: Path & Query Parameters
subtopic: fastapi
group: Routing & Path Operations
order: 2
---

#### Type hints drive parsing & validation

```python
from fastapi import Path, Query
from typing import Annotated

@app.get("/items/{item_id}")
async def get_item(
    item_id: Annotated[int, Path(gt=0)],
    q: Annotated[str | None, Query(max_length=50)] = None,
    skip: int = 0,
    limit: int = 10,
):
    return {"item_id": item_id, "q": q, "skip": skip, "limit": limit}
```

Untyped/plain params are query params by default; params matching `{}` in the path become path params.
