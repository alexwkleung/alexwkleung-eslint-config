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
        "eslint:recommended",
        "plugin:@typescript-eslint/recommended"
    ],
    "parser": "@typescript-eslint/parser",
    "parserOptions": {
        "ecmaVersion": "latest",
        "sourceType": "module"
    }
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
        "react-refresh/only-export-components": "warn"
    }
}
```

2. Create `.eslintignore`

```txt
**/*.js
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
    "source.fixAll.eslint": true
}
```

5. Recommended: Install ESLint and Error Lens extensions in VSCode.
