---
title: Background Tasks
subtopic: fastapi
group: Background Tasks & WebSockets
order: 1
---

#### Run after the response is sent

```python
from fastapi import BackgroundTasks

def send_email(to: str, body: str):
    ...  # slow I/O, runs after response returns

@app.post("/signup")
async def signup(email: str, background_tasks: BackgroundTasks):
    create_user(email)
    background_tasks.add_task(send_email, email, "Welcome!")
    return {"status": "created"}
```

For heavier/queued work, use Celery or an ARQ/RQ worker instead.
