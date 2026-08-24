---
title: Runtime
subtopic: docker
group: Dockerfile Reference
order: 3
---

#### Startup behavior

```dockerfile
EXPOSE 3000                          # documents the port (doesn't publish it)
VOLUME /app/data                     # mount point for external storage
ENTRYPOINT ["node"]                  # fixed executable
CMD ["dist/index.js"]                # default args — overridable at `docker run`
```

With both set, `docker run myapp other.js` runs `node other.js`.
