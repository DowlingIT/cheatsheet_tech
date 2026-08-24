---
title: Async Testing & Overrides
subtopic: fastapi
group: Testing
order: 2
---

#### httpx.AsyncClient + dependency overrides

```python
import pytest
from httpx import AsyncClient, ASGITransport

@pytest.mark.anyio
async def test_list_items():
    transport = ASGITransport(app=app)
    async with AsyncClient(transport=transport, base_url="http://test") as ac:
        response = await ac.get("/items")
    assert response.status_code == 200

# swap a real dependency for a fake in tests
app.dependency_overrides[get_db] = lambda: fake_db_session
```
