---
title: Settings & Environment
subtopic: fastapi
group: "Docs, Config & Deployment"
order: 2
---

#### pydantic-settings

```python
from pydantic_settings import BaseSettings

class Settings(BaseSettings):
    database_url: str
    secret_key: str
    debug: bool = False

    class Config:
        env_file = ".env"

settings = Settings()   # reads env vars / .env automatically

@app.get("/info")
async def info(s: Annotated[Settings, Depends(Settings)]):
    return {"debug": s.debug}
```
