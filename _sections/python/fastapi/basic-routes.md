---
title: Basic Routes
subtopic: fastapi
group: Routing & Path Operations
order: 1
---

#### Path operation decorators

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/items")
async def list_items():
    return [{"name": "Foo"}]

@app.get("/items/{item_id}")
async def get_item(item_id: int):
    return {"item_id": item_id}

@app.post("/items", status_code=201)
async def create_item(name: str):
    return {"name": name}

@app.put("/items/{item_id}")
async def update_item(item_id: int, name: str):
    return {"item_id": item_id, "name": name}

@app.delete("/items/{item_id}", status_code=204)
async def delete_item(item_id: int):
    ...
```
