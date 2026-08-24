---
title: Auto Updates
subtopic: electron
group: Packaging & Distribution
order: 2
---

#### electron-updater

```js
const { autoUpdater } = require('electron-updater');

app.whenReady().then(() => {
  autoUpdater.checkForUpdatesAndNotify();
});

autoUpdater.on('update-downloaded', () => {
  autoUpdater.quitAndInstall();
});
```
