# Cypress

There are huge compatibility issues between vite and cypress and getting them to work together is overly complex as cypress using webpack to build and package code.

# Remove `type` from `package.json`

```
"type": "module",
```

# Install Cypress

```
npm install cypress --save-dev
```

# Configure Cypress

```
npx cypress open
```

# Create file `cypress.d.ts`

```ts
import { mount } from "cypress/react";

// Augment the Cypress namespace to include type definitions for
// your custom command.
// Alternatively, can be defined in cypress/support/component.d.ts
// with a <reference path="./component" /> at the top of your spec.
declare global {
  namespace Cypress {
    interface Chainable {
      mount: typeof mount;
    }
  }
}
```
