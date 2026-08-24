---
title: App Lifecycle
subtopic: electron
group: Main Process
order: 1
---

#### app events

```js
const { app, BrowserWindow } = require('electron');

app.whenReady().then(createWindow);

app.on('window-all-closed', () => {
  if (process.platform !== 'darwin') app.quit();   // macOS apps usually stay open
});

app.on('activate', () => {
  if (BrowserWindow.getAllWindows().length === 0) createWindow();   // macOS dock click
});
```
