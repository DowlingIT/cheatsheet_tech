---
title: Exception Handling
subtopic: fastapi
group: Middleware & Error Handling
order: 2
---

#### HTTPException & custom handlers

```python
from fastapi import HTTPException
from fastapi.responses import JSONResponse

@app.get("/items/{item_id}")
async def get_item(item_id: int):
    if item_id not in db:
        raise HTTPException(status_code=404, detail="Item not found")
    return db[item_id]

class NotEnoughStock(Exception):
    pass

@app.exception_handler(NotEnoughStock)
async def stock_handler(request, exc: NotEnoughStock):
    return JSONResponse(status_code=409, content={"error": "out of stock"})
```
