---
title: OpenAPI Docs
subtopic: fastapi
group: "Docs, Config & Deployment"
order: 1
---

#### Customizing the generated docs

```python
app = FastAPI(
    title="My API",
    description="Does cool things",
    version="1.0.0",
    docs_url="/docs",       # Swagger UI, None to disable
    redoc_url="/redoc",
)

@app.get("/items", tags=["items"], summary="List items",
         response_description="A list of items")
async def list_items():
    """Full markdown **docstring** shown in the docs too."""
    ...
```
