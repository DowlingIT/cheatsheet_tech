---
title: BrowserWindow
subtopic: electron
group: Main Process
order: 2
---

#### Creating a window

```js
function createWindow() {
  const win = new BrowserWindow({
    width: 1000,
    height: 700,
    webPreferences: {
      preload: path.join(__dirname, 'preload.js'),
      contextIsolation: true,     // keep true — isolates preload from page scripts
      nodeIntegration: false,        // keep false — no Node access in the renderer
    },
  });
  win.loadFile('renderer/index.html');
  // win.loadURL('http://localhost:5173');   // e.g. a Vite dev server
}
```
