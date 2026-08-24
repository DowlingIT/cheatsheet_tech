---
title: TestClient
subtopic: fastapi
group: Testing
order: 1
---

#### Sync tests with pytest

```python
from fastapi.testclient import TestClient
from .main import app

client = TestClient(app)

def test_create_item():
    response = client.post("/items", json={"name": "Foo", "price": 4.2})
    assert response.status_code == 201
    assert response.json()["name"] == "Foo"

def test_get_missing_item():
    response = client.get("/items/999")
    assert response.status_code == 404
```
