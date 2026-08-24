---
title: Async Database (SQLModel/SQLAlchemy)
subtopic: fastapi
group: Database
order: 3
---

#### Async engine + session

```python
from sqlalchemy.ext.asyncio import create_async_engine, AsyncSession

engine = create_async_engine("postgresql+asyncpg://user:pass@localhost/db")

async def get_db():
    async with AsyncSession(engine) as session:
        yield session

@app.get("/users/{id}")
async def get_user(id: int, db: Annotated[AsyncSession, Depends(get_db)]):
    result = await db.execute(select(User).where(User.id == id))
    return result.scalar_one_or_none()
```
