---
title: Main → Renderer
subtopic: electron
group: IPC
order: 2
---

#### send / on (one-way push)

```js
// main.js
win.webContents.send('update-available', { version: '2.0.0' });

// preload.js
contextBridge.exposeInMainWorld('api', {
  onUpdate: (callback) => ipcRenderer.on('update-available', (e, data) => callback(data)),
});

// renderer
window.api.onUpdate((data) => console.log('Update:', data.version));
```
