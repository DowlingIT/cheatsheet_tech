---
title: Environment & Config
subtopic: express
group: Config & Deployment
order: 1
---

#### dotenv & app settings

```js
require('dotenv').config();

const PORT = process.env.PORT || 3000;
app.listen(PORT, () => console.log(`Listening on ${PORT}`));

app.set('trust proxy', 1);      // needed behind a reverse proxy (nginx, Heroku)
app.disable('x-powered-by');      // hide the Express fingerprint header
```
