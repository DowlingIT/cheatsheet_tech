---
title: Multi-stage Builds
subtopic: docker
group: Images
order: 3
---

#### Slim final image

```dockerfile
# --- build stage ---
FROM node:20 AS build
WORKDIR /app
COPY . .
RUN npm ci && npm run build

# --- runtime stage ---
FROM node:20-slim
WORKDIR /app
COPY --from=build /app/dist ./dist
CMD ["node", "dist/index.js"]
```

`--from=build` copies only the artifacts you need, leaving build tools behind.
