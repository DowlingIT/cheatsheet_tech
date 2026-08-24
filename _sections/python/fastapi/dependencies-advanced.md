---
title: Class & Yield Dependencies
subtopic: fastapi
group: Dependency Injection
order: 2
---

#### Classes as dependencies, cleanup with yield

```python
class Paginator:
    def __init__(self, skip: int = 0, limit: int = 10):
        self.skip, self.limit = skip, limit

@app.get("/items")
async def list_items(p: Annotated[Paginator, Depends()]):
    return {"skip": p.skip, "limit": p.limit}

async def get_db():
    db = SessionLocal()
    try:
        yield db          # code before yield = setup
    finally:
        db.close()         # code after yield = teardown, runs after response
```
