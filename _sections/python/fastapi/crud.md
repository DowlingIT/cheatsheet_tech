---
title: CRUD with DB Session
subtopic: fastapi
group: Database
order: 2
---

#### Inject the session per-request

```python
from sqlalchemy.orm import Session

def get_db():
    db = SessionLocal()
    try:
        yield db
    finally:
        db.close()

@app.post("/users", response_model=schemas.User)
def create_user(user: schemas.UserCreate, db: Annotated[Session, Depends(get_db)]):
    db_user = models.User(email=user.email)
    db.add(db_user)
    db.commit()
    db.refresh(db_user)
    return db_user
```
