---
title: API Keys & Password Hashing
subtopic: fastapi
group: Auth & Security
order: 2
---

#### APIKeyHeader + passlib

```python
from fastapi.security import APIKeyHeader
from passlib.context import CryptContext

api_key_header = APIKeyHeader(name="X-API-Key")

async def verify_key(key: Annotated[str, Depends(api_key_header)]):
    if key != settings.API_KEY:
        raise HTTPException(status_code=403, detail="Invalid API key")

pwd_context = CryptContext(schemes=["bcrypt"], deprecated="auto")
hashed = pwd_context.hash("plaintext")
pwd_context.verify("plaintext", hashed)   # -> True
```
