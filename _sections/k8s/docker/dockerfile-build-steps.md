---
title: Build Steps
subtopic: docker
group: Dockerfile Reference
order: 2
---

#### Assembling the image

```dockerfile
WORKDIR /app
COPY package*.json ./          # copy first for layer caching
RUN npm ci
COPY . .                       # then the rest of the source
ADD archive.tar.gz /opt/       # like COPY, but auto-extracts archives
USER node                      # drop root for the remaining steps
```

Prefer `COPY` over `ADD` unless you need auto-extraction or remote URLs.
