# @frontendfixer/stylelint-config-standard

![npm](https://img.shields.io/npm/v/%40frontendfixer%2Fstylelint-config-standard?style=social&logo=npm&logoColor=%23ff5555) ![GitHub Workflow Status (with event)](https://img.shields.io/github/actions/workflow/status/frontendfixer/-frontendfixer-stylelint-config-standard/release.yml?style=social&logo=github) ![GitHub](https://img.shields.io/github/license/frontendfixer/-frontendfixer-stylelint-config-standard)

Stylelint config with standard rules and useful plugins

---

## Packages included

- plugins
  - [stylelint-scss](https://github.com/stylelint-scss/stylelint-scss)
- Config Extended
  - [stylelint-config-standard](https://github.com/stylelint/stylelint-config-standard)
  - [stylelint-config-standard-scss](https://github.com/stylelint/stylelint-config-standard-scss)
  - [stylelint-config-css-modules](https://github.com/pascalduez/stylelint-config-css-modules)
  - [stylelint-config-recess-order](https://github.com/stormwarning/stylelint-config-recess-order)
- [postcss-scss](https://github.com/postcss/postcss-scss)

---

## Usages

### Installation

```bash
yarn add -D postcss^8.4.27 stylelint^15.10.2 @frontendfixer/stylelint-config-standard

```

### Configuration

Create a Stylelint config file with `.stylelintrc` or `.stylelintrc.json` and put this lint

```json
{
  "extends": "@frontendfixer/stylelint-config-standard"
}
```

or you can also put it in your `package.json` above scripts or higher position

```json
"stylelint": {
    "extends": "@frontendfixer/stylelint-config-standard"
  }
```

### Add script

You can add two scripts to your package.json to lint and/or fix:

```json
"scripts": {
  "lint": "stylelint '**/*.{css,scss}'",
  "lint:fix": "stylelint '**/*.{css,scss}' --fix",
},
```

- Now you can manually lint your code by running `yarn run lint` and fix all fixable issues with `yarn run lint:fix`. You probably want your editor to do this though.

### Auto fix lint error with VSCode

You should read this entire thing. Serious!

Once you have done one, or both, of the above installs. You probably want your editor to lint and fix for you. Here are the instructions for VS Code:

1. Install the [vscode-stylelint](https://marketplace.visualstudio.com/items?itemName=stylelint.vscode-stylelint)
2. Now we need to setup some VS Code settings via `Code/File` → `Preferences` → `Settings`. It's easier to enter these settings while editing the `settings.json` file, so click the Open (Open Settings) icon in the top right corner:

```js
// disable the built-in CSS, Less, and SCSS linters:
"css.validate": false,
"scss.validate": false,
// enable stylelint
"stylelint.validate": ["css", "scss"],
// tell the Stylelint plugin to run on save
"editor.codeActionsOnSave": {
  "source.fixAll.stylelint": true
},
```
