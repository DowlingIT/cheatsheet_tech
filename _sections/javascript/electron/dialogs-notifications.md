---
title: Dialogs & Notifications
subtopic: electron
group: Native UI
order: 2
---

#### Native dialogs

```js
const { dialog, Notification } = require('electron');

const { filePaths } = await dialog.showOpenDialog({ properties: ['openFile'] });
await dialog.showMessageBox({ message: 'Saved!', type: 'info' });

new Notification({ title: 'Done', body: 'Export finished' }).show();
```
