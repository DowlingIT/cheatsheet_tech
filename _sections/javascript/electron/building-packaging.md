---
title: Building & Packaging
subtopic: electron
group: Packaging & Distribution
order: 1
---

#### electron-builder

```bash
npm install -D electron-builder

npx electron-builder --win --mac --linux
npx electron-builder --publish never    # build without publishing
```

```json
"build": {
  "appId": "com.example.myapp",
  "win": { "target": "nsis" },
  "mac": { "target": "dmg" }
}
```
