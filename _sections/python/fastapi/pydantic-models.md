---
title: Pydantic Models
subtopic: fastapi
group: Pydantic Models & Validation
order: 1
---

#### Request bodies as models

```python
from pydantic import BaseModel

class Item(BaseModel):
    name: str
    description: str | None = None
    price: float
    tags: list[str] = []

@app.post("/items")
async def create_item(item: Item):
    return item.model_dump()
```

FastAPI reads the type hint, parses JSON body, validates it, and returns `422` on failure.
