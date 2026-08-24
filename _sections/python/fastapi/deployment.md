---
title: Running & Deployment
subtopic: fastapi
group: "Docs, Config & Deployment"
order: 3
---

#### Production server

```bash
# multiple worker processes behind uvicorn's ASGI workers
gunicorn main:app -k uvicorn.workers.UvicornWorker -w 4 -b 0.0.0.0:8000
```

```dockerfile
FROM python:3.12-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
CMD ["fastapi", "run", "main.py", "--port", "8000"]
```
