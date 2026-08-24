---
title: Preload Scripts & contextBridge
subtopic: electron
group: Renderer & Preload
order: 1
---

#### Exposing a safe API

```js
// preload.js
const { contextBridge, ipcRenderer } = require('electron');

contextBridge.exposeInMainWorld('api', {
  getVersion: () => ipcRenderer.invoke('app:getVersion'),
  onUpdate: (callback) => ipcRenderer.on('update-available', callback),
});

// renderer/index.js
const version = await window.api.getVersion();   // no direct Node/ipcRenderer access
```
