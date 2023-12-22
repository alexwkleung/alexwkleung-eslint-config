# eslint-config

ESLint config. 

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

Install Prettier (optional)

```bash
npm install prettier eslint-plugin-prettier eslint-config-prettier
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

TypeScript + Prettier

```bash
npm install eslint @typescript-eslint/eslint-plugin @typescript-eslint/parser prettier eslint-plugin-prettier eslint-config-prettier --save-dev
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

TypeScript + Prettier:

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
            "plugin:@typescript-eslint/recommended",
            "plugin:prettier/recommended",
            "prettier"
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

3. Create `.prettierrc.json` (optional)

```json
{
    "trailingComma": "es5",
    "tabWidth": 4,
    "semi": true,
    "singleQuote": false
}
```

4. Add scripts to `package.json`

```json
"scripts": {
    "eslint": "eslint .",
    "eslint:fix": "eslint . --fix"
}
```

5. Add these to VS Code `settings.json`

```json
"editor.codeActionsOnSave": {
    "source.fixAll.eslint": "always",
    "editor.formatOnSave": "always"
},
"prettier.enable": true
```

6. Recommended: Install ESLint, Prettier, and Error Lens extensions in VSCode.
