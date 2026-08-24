---
title: Response Models
subtopic: fastapi
group: Response Handling
order: 1
---

#### Shape & filter the output

```python
class UserOut(BaseModel):
    id: int
    email: str
    # password never included -> excluded from response

@app.post("/users", response_model=UserOut, status_code=201)
async def create_user(user: UserIn):
    return db_create_user(user)   # extra fields silently stripped

@app.get("/users", response_model=list[UserOut])
async def list_users():
    ...
```
