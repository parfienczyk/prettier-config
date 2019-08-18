# ESLint + Prettier + Typescript

Default configuration for ESLint + Prettier + Typescript


## Installation

```
npm i -D @typescript-eslint/eslint-plugin @typescript-eslint/parser
```


```
npm i -D eslint eslint-config-prettier eslint-config-react eslint-plugin-prettier prettier
```



### Preview of devDependecies in package.json

```js
  "devDependencies": {
    "@typescript-eslint/eslint-plugin": "^2.0.0",
    "@typescript-eslint/parser": "^2.0.0",
    "eslint": "^6.1.0",
    "eslint-config-prettier": "^6.0.0",
    "eslint-plugin-prettier": "^3.1.0",
    "eslint-plugin-react": "^7.14.3",
    "eslint-plugin-react-hooks": "1.7.0",
    "prettier": "^1.18.2"
  },
```

Add two files in project (root level)

```
.eslintignore
.eslintrc.json
```

And our file `eslintrc.js` should looks like this

```js
{
  "extends": [
    "eslint:recommended",
    "plugin:react/recommended",
    "plugin:@typescript-eslint/recommended",
    "prettier/@typescript-eslint",
    "plugin:prettier/recommended"
  ],
  "plugins": ["react", "@typescript-eslint", "prettier"],
  "env": {
    "browser": true,
    "jasmine": true,
    "jest": true
  },
  "rules": {},
  "settings": {
    "react": {
      "pragma": "React",
      "version": "detect"
    }
  },
  "parser": "@typescript-eslint/parser"
}
```


## VS Code

Automatically Fixing Code (VS Code)

For a good developer experience, it's useful to setup your editor to automatically run ESLint's automatic fix command (i.e. `eslint --fix`) whenever a file is saved. Since i'm using VS Code, here is the config required in the `settings.json` file in VS Code to get automatic fixing whenever saving a file:

```js
"eslint.autoFixOnSave":  true,
"eslint.validate":  [
  "javascript",
  "javascriptreact",
  {"language":  "typescript",  "autoFix":  true  },
  {"language":  "typescriptreact",  "autoFix":  true  }
],

"editor.formatOnSave":  true,
"editor.formatOnPaste":  true,
```

