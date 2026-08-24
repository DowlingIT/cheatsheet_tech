---
title: Core Concepts
subtopic: fastapi
group: Terminology & Structure
order: 1
---

#### Terms

```
Path operation        a route: a path + HTTP method bound to a function
ASGI                   async server gateway interface (vs WSGI); FastAPI runs on it
Uvicorn                 ASGI server used to run FastAPI apps
Pydantic model            class defining request/response shape + validation
Dependency (Depends)         reusable value/logic injected into a path operation
APIRouter                    mountable group of path operations, like a mini-app
Middleware                     function that wraps every request/response
```
