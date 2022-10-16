# gustavthron.github.io

[https://gustavthron.github.io/](https://gustavthron.github.io/)

## Git

To only push files with LF, create `.gitattributes` containing:

```
* text=auto
```

## Create React App

Install `create-react-app`.

Run:

```
npx create-react-app . --template typescript
```

## TypeScript

Allow absolute path in import by adding to `tsconfig.json`:

```json
{
  "baseUrl": "src"
}
```

## Github Pages

[https://create-react-app.dev/docs/deployment/#github-pages](https://create-react-app.dev/docs/deployment/#github-pages)

Install `gh-pages`.

Add to `package.json`:

```json
{
  "homepage": "<GITHUB_PAGE_URL>",
  "scripts": {
    "predeploy": "npm run build",
    "deploy": "gh-pages -b <GITHUB_PAGE_BRANCH> -d build"
  }
}
```

## ESLint

Install `eslint`.

Run:

```
npx eslint --init
```

Install:

- `eslint-plugin-react` - Linting for React
- `eslint-plugin-react-hooks` - Linting for React Hooks
- `eslint-plugin-jsx-a11y` - Linting for JSX
- `eslint-plugin-import` - Recommended
- `eslint-import-resolver-typescript` - Needed when using `eslint-plugin-import` and TypeScript
- `@typescript-eslint/eslint-plugin` - Linting for TypeScript
- `@typescript-eslint/parser` - Parser for TypeScript
- `eslint-config-prettier` - Remove rules handled by Prettier

Create `.eslintignore` file:

```
build
node_modules
```

Configure ESLint, for example in `.eslintrc.json`:

```json
{
  "env": {
    "browser": true,
    "es2021": true
  },
  "extends": [
    "eslint:recommended",
    "plugin:@typescript-eslint/recommended",
    "plugin:@typescript-eslint/recommended-requiring-type-checking",
    "plugin:import/recommended",
    "plugin:import/typescript",
    "plugin:jsx-a11y/recommended",
    "plugin:react/recommended",
    "plugin:react/jsx-runtime",
    "plugin:react-hooks/recommended",
    "prettier",
    "react-app" // From Create React App
  ],
  // For TypeScript:
  "parser": "@typescript-eslint/parser",
  "parserOptions": {
    "ecmaFeatures": {
      "jsx": true
    },
    "ecmaVersion": "latest",
    "project": "./tsconfig.json",
    "sourceType": "module"
  },
  // Don't search for ESLint config files in parent folders.
  "root": true,
  // For `eslint-import-resolver-typescript`.
  "settings": {
    "import/resolver": {
      "typescript": {
        "project": "./tsconfig.json"
      },
      "node": true
    }
  }
}
```

## Prettier

Install `prettier`.

Configure Prettier, for example in `.prettierrc.json`:

```json
{
  "arrowParens": "always",
  "bracketSpacing": true,
  "printWidth": 80,
  "semi": true,
  "singleQuote": true,
  "tabWidth": 2,
  "trailingComma": "all",
  "useTabs": false
}
```

### Pre-commit

[https://prettier.io/docs/en/precommit.html](https://prettier.io/docs/en/precommit.html)

Run Prettier automatically with pre-commit hook.

Install `husky` and `pretty-quick`.

Run:

```
npm set-script prepare "husky install"
npm run prepare
npx husky add .husky/pre-commit "npx pretty-quick --staged"
```

## File structure

```
public/
  images/
    icon/
      android-chrome-192x192.png
      android-chrome-512x512.png
      apple-touch-icon.png
      favicon-16x16.png
  index.html
  manifest.json
  robots.txt
src/
  components/
    Component/
      index.tsx
      Component.module.css
      Component.test.tsx
      Component.tsx
  containers/
    App/
      App.css
      App.test.tsx
      App.tsx
      index.tsx
    Container/
      index.tsx
      Container.module.css
      Container.test.tsx
      Container.tsx
  hooks/
    UseHook/
      index.tsx
      UseHook.test.tsx
      UseHook.tsx
  images/
  index.css
  index.test.tsx
  index.tsx
```

## CSS

[https://elad.medium.com/normalize-css-or-css-reset-9d75175c5d1e](https://elad.medium.com/normalize-css-or-css-reset-9d75175c5d1e)
