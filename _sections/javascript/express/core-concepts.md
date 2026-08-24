---
title: Core Concepts
subtopic: express
group: Terminology & Structure
order: 1
---

#### Terms

```
Middleware              function with (req, res, next) that runs during the request cycle
Route handler              middleware bound to a specific method + path
next()                        hands off to the next middleware/handler in the chain
Router                          mini, mountable instance of Express routes/middleware
app                                the Express application instance
Error-handling middleware           middleware with 4 args (err, req, res, next)
```
