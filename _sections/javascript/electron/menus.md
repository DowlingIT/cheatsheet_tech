---
title: Menus
subtopic: electron
group: Native UI
order: 1
---

#### Application & context menus

```js
const { Menu } = require('electron');

const template = [
  { label: 'File', submenu: [{ role: 'quit' }] },
  { label: 'Edit', submenu: [{ role: 'copy' }, { role: 'paste' }] },
];
Menu.setApplicationMenu(Menu.buildFromTemplate(template));

const contextMenu = Menu.buildFromTemplate([{ label: 'Inspect', click: () => {} }]);
win.webContents.on('context-menu', () => contextMenu.popup());
```
