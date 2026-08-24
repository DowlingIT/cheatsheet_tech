---
title: System Integration
subtopic: electron
group: Windows & System
order: 2
---

#### shell & paths

```js
const { shell, app } = require('electron');

shell.openExternal('https://example.com');   // open in the default browser
shell.showItemInFolder(filePath);              // reveal in the file explorer

app.getPath('userData');    // per-user app data directory
app.getPath('downloads');
app.getVersion();   app.getName();
```
