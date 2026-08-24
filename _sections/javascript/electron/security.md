---
title: Security Best Practices
subtopic: electron
group: Security
order: 1
---

#### Checklist

```
contextIsolation: true        keeps the preload scope separate from page scripts
nodeIntegration: false           never expose Node APIs directly to remote/untrusted content
sandbox: true                       runs the renderer in Chromium's OS-level sandbox
Only load trusted content              avoid loadURL() with untrusted/remote input
Set a Content-Security-Policy             restricts what scripts/resources can run
Validate all IPC input                       treat renderer messages like untrusted input
```
