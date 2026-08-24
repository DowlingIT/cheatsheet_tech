---
title: Field Validation
subtopic: fastapi
group: Pydantic Models & Validation
order: 2
---

#### Constraints & custom validators

```python
from pydantic import BaseModel, Field, field_validator, EmailStr

class User(BaseModel):
    email: EmailStr
    age: int = Field(gt=0, le=120)
    username: str = Field(min_length=3, max_length=20)

    @field_validator("username")
    @classmethod
    def no_spaces(cls, v: str) -> str:
        if " " in v:
            raise ValueError("username must not contain spaces")
        return v
```
