### Performing Type Checks and ESLint Checks

#### Type Check

To perform a type check in a TypeScript project, use the following command:

```bash
npx tsc --noEmit

# The --noEmit flag tells TypeScript to perform a type check without generating any output files. 
# This will only check for type errors in your code.

#### ESLint Errors

# To check for ESLint errors in your project, run:

```bash
npx eslint .

# If you want to automatically fix errors that ESLint can correct, add the --fix flag:

```bash
npx eslint . --fix

# Alternatively, if you have a script in your package.json, you can run:
```bash
npm run lint

# This will show any linting errors or warnings in your project and fix them if possible.
