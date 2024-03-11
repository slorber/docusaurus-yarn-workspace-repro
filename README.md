# Docusaurus Workspaces Import Issue Repro

```sh
# Init dir and docusaurus with Yarn workspaces.
git init
mkdir packages
yarn create docusaurus docs classic packages

mv packages/docs/docs .
sed -i 's/sidebarPath/path: "..\/..\/docs",\n          sidebarPath/' packages/docs/docusaurus.config.js

# This works correctly
cd packages/docs && yarn start
```
