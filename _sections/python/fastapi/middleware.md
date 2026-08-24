---
title: Middleware
subtopic: fastapi
group: Middleware & Error Handling
order: 1
---

#### Custom middleware & CORS

```python
import time
from fastapi.middleware.cors import CORSMiddleware

@app.middleware("http")
async def add_timing_header(request, call_next):
    start = time.time()
    response = await call_next(request)
    response.headers["X-Process-Time"] = str(time.time() - start)
    return response

app.add_middleware(
    CORSMiddleware,
    allow_origins=["https://example.com"],
    allow_methods=["*"],
    allow_headers=["*"],
)
```
