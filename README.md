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


###Prettier (Code Formatting):

#Use Prettier to auto-format your code. You can run 
```bash
npx prettier --write . 

#to format your entire codebase before committing.


###Unit Tests:

Set up unit tests using a framework like Jest or React Testing Library.
Run 
```bash
npm test 
##to ensure all tests pass before committing.


##Husky (Git Hooks):

#Install Husky to automate pre-commit checks like linting, formatting, and testing:
```bash
npx husky-init && npm install


Add a pre-commit hook to run tests, linting, or formatting before code gets committed:
```bash
npx husky set .husky/pre-commit 

```bash
npm run lint && npm test