---
title: Request Body
subtopic: fastapi
group: Pydantic Models & Validation
order: 3
---

#### Nested & multiple bodies

```python
class Address(BaseModel):
    city: str
    zip_code: str

class User(BaseModel):
    name: str
    address: Address           # nested model

@app.post("/orders")
async def create_order(user: User, item: Item):
    # two body params -> {"user": {...}, "item": {...}}
    return {"user": user, "item": item}

@app.post("/orders/single")
async def create_order_embed(item: Item = Body(embed=True)):
    # forces {"item": {...}} even with one body param
    return item
```
