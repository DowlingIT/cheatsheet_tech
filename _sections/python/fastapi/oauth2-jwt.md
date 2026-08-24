---
title: OAuth2 & JWT
subtopic: fastapi
group: Auth & Security
order: 1
---

#### Password flow + bearer token

```python
from fastapi.security import OAuth2PasswordBearer, OAuth2PasswordRequestForm
import jwt

oauth2_scheme = OAuth2PasswordBearer(tokenUrl="token")

@app.post("/token")
async def login(form: Annotated[OAuth2PasswordRequestForm, Depends()]):
    user = authenticate(form.username, form.password)
    token = jwt.encode({"sub": user.username}, SECRET_KEY, algorithm="HS256")
    return {"access_token": token, "token_type": "bearer"}

async def get_current_user(token: Annotated[str, Depends(oauth2_scheme)]):
    payload = jwt.decode(token, SECRET_KEY, algorithms=["HS256"])
    return payload["sub"]

@app.get("/me")
async def read_me(user: Annotated[str, Depends(get_current_user)]):
    return {"user": user}
```
