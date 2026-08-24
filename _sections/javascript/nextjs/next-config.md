---
title: next.config.js
subtopic: nextjs
group: Config & CLI
order: 1
---

#### Common options

```js
/** @type {import('next').NextConfig} */
const nextConfig = {
  reactStrictMode: true,
  images: { domains: ['example.com'] },
  env: { API_URL: process.env.API_URL },
  async redirects() {
    return [{ source: '/old', destination: '/new', permanent: true }];
  },
};
module.exports = nextConfig;
```
