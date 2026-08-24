---
title: Multiple Windows & Tray
subtopic: electron
group: Windows & System
order: 1
---

#### Managing windows & a tray icon

```js
let mainWindow, settingsWindow;

function openSettings() {
  settingsWindow = new BrowserWindow({ parent: mainWindow, modal: true });
  settingsWindow.loadFile('renderer/settings.html');
}

const { Tray } = require('electron');
const tray = new Tray('icon.png');
tray.setToolTip('My App');
tray.on('click', () => mainWindow.show());
```
