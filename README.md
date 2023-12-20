# eslint-config

My ESLint config.

# Installation

Install ESLint 

```bash
npm install eslint --save-dev
```

Install TypeScript ESLint packages

```bash
npm install @typescript-eslint/eslint-plugin --save-dev

npm install @typescript-eslint/parser --save-dev
```

If you are using React, install React ESLint packages as well

```bash
npm install eslint-plugin-react-hooks --save-dev

npm install eslint-plugin-react-refresh --save-dev
```


**Alternatively, use one-liner install:** 

TypeScript

```bash
npm install eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser --save-dev
```

React

```bash
npm install eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser eslint-plugin-react-hooks eslint-plugin-react-refresh --save-dev
```

# Setup

1. Create `.eslintrc.json`

TypeScript:

```json
{
    "env": {
        "browser": true,
        "es2021": true
    },
    "extends": [
        "eslint:recommended"
    ],
    "parserOptions": {
        "ecmaVersion": "latest",
        "sourceType": "module"
    },
    "overrides": [{
        "files": ["*.ts", "*.mts", "*.d.ts"],
        "extends": [
            "plugin:@typescript-eslint/recommended"
        ],
        "parser": "@typescript-eslint/parser",
        "plugins": [
            "@typescript-eslint"
        ],
        "rules": {
            "@typescript-eslint/explicit-function-return-type": "error",
            "@typescript-eslint/no-inferrable-types": "off",
            "@typescript-eslint/no-explicit-any": "warn"
        }
    }]
}
```

React: 

```json
{
    "env": {
        "browser": true,
        "es2021": true
    },
    "extends": [
        "eslint:recommended",
        "plugin:@typescript-eslint/recommended",
        "plugin:react-hooks/recommended"
    ],
    "parser": "@typescript-eslint/parser",
    "parserOptions": {
        "ecmaVersion": "latest",
        "sourceType": "module"
    },
    "plugins": ["react-refresh"],
    "rules": {
        "react-refresh/only-export-components": "warn",
        "@typescript-eslint/explicit-function-return-type": "error",
        "@typescript-eslint/no-inferrable-types": "off",
        "@typescript-eslint/no-explicit-any": "warn"
    }
}
```

2. Create `.eslintignore`

```txt
**/*.js
node_modules
dist
out
build
.gitignore
```

3. Add scripts to `package.json`

```json
"scripts": {
    "eslint": "eslint .",
    "eslint:fix": "eslint . --fix"
}
```

4. Add lint on save to VSCode `settings.json`

```json
"editor.codeActionsOnSave": {
    "source.fixAll.eslint": "always"
}
```

5. Recommended: Install ESLint and Error Lens extensions in VSCode.
