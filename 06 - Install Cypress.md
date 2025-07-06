# Cypress

Installing cypress is simple, but can take a few minutes to setup.

# Remove `type` from `package.json`

It is important to remove the type attribute from the package.json file or cypress will not be able to process its settings correctly and will fail the setup procedure.

```
"type": "module",
```

# Install Cypress

```
npm install cypress --save-dev
```

# Configure Cypress

The procedure will take a few moments.

```
npx cypress open
```

# Create file type definition file

Create the following type definition file.

create a file in the root directory named `cypress.d.ts`.

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
