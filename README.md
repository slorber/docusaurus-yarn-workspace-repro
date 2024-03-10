# Docusaurus Workspaces Import Issue Repro

```sh
# Init dir and docusaurus with Yarn workspaces.
git init
yarn init -2 -w
yarn create docusaurus docs classic packages

# This works at this point
yarn workspace docs start


# Move docs dir out of the docusaurus directory and update config.
mv packages/docs/docs .
sed -i 's/sidebarPath/path: "..\/..\/docs",\n          sidebarPath/' packages/docs/docusaurus.config.js

# This no longer works
yarn workspace docs start
```
