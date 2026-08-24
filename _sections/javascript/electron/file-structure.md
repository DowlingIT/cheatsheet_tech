---
title: File Structure
subtopic: electron
group: Terminology & Structure
order: 2
---

#### Typical layout

```
main.js              entry point — the main process
preload.js             preload script, exposes a safe API via contextBridge
renderer/                 renderer process code (HTML/CSS/JS or a framework)
  index.html
  index.js
package.json                "main" field points to main.js
electron-builder.yml           packaging config (if using electron-builder)
```
