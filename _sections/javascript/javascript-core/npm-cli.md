---
title: npm CLI
subtopic: javascript-core
group: Modules & Packages
order: 2
---

#### Packages

```bash
npm init -y                          # create package.json
npm install lodash                    # add & install (dependencies)
npm install -D eslint                 # dev-only dependency
npm install lodash@4.17.21            # pinned version

npm ci                                 # install exactly from package-lock.json (CI)
npm update                              # update within allowed ranges
npm uninstall lodash
```

#### Info & scripts

```bash
npm list                     # installed packages
npm outdated                  # packages with newer versions available
npm run <script>                # run a package.json script
npx <package>                     # run a package without installing it globally
```
