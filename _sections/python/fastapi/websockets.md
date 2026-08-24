---
title: WebSockets
subtopic: fastapi
group: Background Tasks & WebSockets
order: 2
---

#### WebSocket endpoint

```python
from fastapi import WebSocket, WebSocketDisconnect

@app.websocket("/ws/{client_id}")
async def ws_endpoint(websocket: WebSocket, client_id: int):
    await websocket.accept()
    try:
        while True:
            data = await websocket.receive_text()
            await websocket.send_text(f"Echo: {data}")
    except WebSocketDisconnect:
        print(f"Client {client_id} disconnected")
```
