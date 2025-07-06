## Fast Refresh via SWC (alternative to Babel)

To enable Fast Refresh using SWC, a high-performance JavaScript/TypeScript compiler written in Rust, install the official Vite React SWC plugin:

This replaces the default Babel-based plugin and offers significantly faster build and HMR times, especially in larger codebases.

```
npm install --save-dev @vitejs/plugin-react-swc
```

## Linting: React-Specific Best Practices

This plugin provides additional lint rules for React components and JSX beyond what's covered by base ESLint or eslint-plugin-react.

```
npm install --save-dev eslint-plugin-react-x
```

## To catch incorrect or risky use of React DOM APIs

This plugin helps identify and prevent misuse of React DOM methods and patterns, improving code safety and consistency.

```
npm install --save-dev eslint-plugin-react-dom
```

## To catch incorrect use of hooks

This plugin enforces the Rules of Hooks in React. It helps ensure correct usage of useEffect, useState, useCallback, etc.

```
npm install --save-dev eslint-plugin-react-hooks
```

## Update the esLint configuration

eslint.config.js:

```
import { globalIgnores } from "eslint/config";
import globals from "globals";
import js from "@eslint/js";
import react from "eslint-plugin-react";
import reactHooks from "eslint-plugin-react-hooks";
import reactRefresh from "eslint-plugin-react-refresh";
import tseslint from "typescript-eslint";

export default tseslint.config([
  globalIgnores(["dist"]),
  {
    files: ["**/*.{ts,tsx}"],
    extends: [
      js.configs.recommended,
      tseslint.configs.recommended,
      react.configs.recommended,
      reactHooks.configs["recommended-latest"],
      reactRefresh.configs.vite,
    ],
    languageOptions: {
      ecmaVersion: 2020,
      globals: globals.browser,
    },
  },
]);


```
