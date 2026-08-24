---
title: File Structure
subtopic: express
group: Terminology & Structure
order: 2
---

#### Typical layout

```
src/
  app.js                Express app setup, middleware registration
  server.js               starts the HTTP server, listens on a port
  routes/                    one file per resource — mounted onto app/Router
    users.js
  controllers/                 request handlers, separated from routing
  middleware/                     custom middleware (auth, error handler, logging)
  models/                            data layer (Mongoose/Prisma/etc.)
  .env                                 environment variables
```
