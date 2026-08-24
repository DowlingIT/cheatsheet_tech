---
title: Renderer Process
subtopic: electron
group: Renderer & Preload
order: 2
---

#### Loading content & devtools

```js
win.loadFile('renderer/index.html');
win.loadURL('https://example.com');
win.webContents.openDevTools();
```

The renderer is a normal web page — it cannot use `require()` or Node APIs directly unless explicitly exposed through a preload script.
