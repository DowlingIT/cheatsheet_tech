---
title: Custom Responses
subtopic: fastapi
group: Response Handling
order: 2
---

#### Response classes

```python
from fastapi.responses import (
    JSONResponse, HTMLResponse, RedirectResponse,
    StreamingResponse, FileResponse,
)

@app.get("/raw")
async def raw():
    return JSONResponse(content={"ok": True}, status_code=200)

@app.get("/page", response_class=HTMLResponse)
async def page():
    return "<h1>Hello</h1>"

@app.get("/download")
async def download():
    return FileResponse("report.pdf", filename="report.pdf")
```
