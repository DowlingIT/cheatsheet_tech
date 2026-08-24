---
title: SQLAlchemy Setup
subtopic: fastapi
group: Database
order: 1
---

#### Engine, session, base

```python
# database.py
from sqlalchemy import create_engine
from sqlalchemy.orm import sessionmaker, declarative_base

engine = create_engine("postgresql://user:pass@localhost/db")
SessionLocal = sessionmaker(autocommit=False, bind=engine)
Base = declarative_base()

# models.py
class User(Base):
    __tablename__ = "users"
    id = Column(Integer, primary_key=True)
    email = Column(String, unique=True, index=True)
```
