---
title: Core Concepts
subtopic: electron
group: Terminology & Structure
order: 1
---

#### Process model

```
Main process           one Node.js process — creates windows, has full OS access
Renderer process           one per BrowserWindow — runs web content (Chromium)
Preload script                 runs before renderer content loads, bridges main ↔ renderer
IPC                               Inter-Process Communication — how main/renderer talk
contextBridge                        safely exposes APIs from preload to the renderer
BrowserWindow                           a native OS window hosting a renderer process
```
