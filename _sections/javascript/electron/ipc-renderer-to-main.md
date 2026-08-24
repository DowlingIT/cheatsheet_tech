---
title: Renderer → Main
subtopic: electron
group: IPC
order: 1
---

#### invoke / handle (request-response)

```js
// preload.js
contextBridge.exposeInMainWorld('api', {
  saveFile: (data) => ipcRenderer.invoke('file:save', data),
});

// main.js
ipcMain.handle('file:save', async (event, data) => {
  await fs.writeFile('out.txt', data);
  return { ok: true };
});

// renderer
const result = await window.api.saveFile('hello');
```
