# prettier-config

A simple Prettier configuration in a lightweight npm package used at [Chaine](https://chaineapp.com/). Use this to standarize code format for your project or accross teams in a large project.

# Quick Start

If you have Prettier already configured, simply install and use:

```sh
npm install --save-dev @chaine/prettier-config
```

Add prettier key to package.json to use config in your project:

```
"prettier": "@chaine/prettier-config",
```

# Config details

```js
{
  printWidth: 120,
  tabWidth: 2,
  semi: false,
  singleQuote: true,
  bracketSpacing: false,
  trailingComma: 'none',
  arrowParens: 'avoid'
}
```

[Check out the `prettier` documentation for more info on sharing configurations](https://prettier.io/docs/en/configuration.html#sharing-configurations).

# Set up in 3 steps

Instructions if you have never used Prettier before.

## 1. Prerequisite

Prettier must be installed as a dev dependency

```sh
npm install --save-dev --save-exact prettier
```

## 2. Install package and update package.json

Install the package using `npm` (or `yarn`)

```sh
npm install --save-dev @chaine/prettier-config
```

Add the `prettier` key to your `package.json`

```diff
diff --git a/package.json b/package.json
index 2ecef3d..260838f 100644
--- a/package.json
+++ b/package.json
@@ -5,6 +5,7 @@
   "keywords": [
     "prettier"
   ],
+  "prettier": "@chaine/prettier-config",
   "license": "MIT",
   "author": "Chaine Inc.",
   "main": "index.js"
```

## 3. VSCode Setup

To use the Prettier we have just installed from VSCode we need to install the [Prettier VSCode extension](https://github.com/prettier/prettier-vscode):

In VSCode terminal, run the following command:

```sh
ext install esbenp.prettier-vscode
```

Open .vscode/settings.json file and confirm:

- VSCode Prettier extension is configured as the default formatter.
- Formatting on save is enabled `.vscode/settings.json`

```json
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true
}
```

# Extend or override this configuration

If you want to extend or this configuration or override any of the options for a specific project or repo, first import the configuration in a `.prettierrc.js` file and then export the modifications.
[See here for more details] (https://prettier.io/docs/en/configuration.html#sharing-configurations)

```js
module.exports = {
  ...require('@chaine/prettier-config'),
  semi: false,
  ...[options]
}
```
