### Performing Checks on code Full instructions 

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


Husky (Git Hooks):

Install Husky to automate pre-commit checks like linting, formatting, and testing:
```bash
npx husky-init && npm install


Add a pre-commit hook to run tests, linting, or formatting before code gets committed:
```bash
npx husky set .husky/pre-commit 

```bash
npm run lint && npm test







### Usefull libraries 

1. Icon libaries
    - https://lucide.dev/
2. Illustration Libaries
    - https://undraw.co/
3. Domain search 
    - https://osint.sh/   



Use Commit Types Consistently: Stick to common types like:

feat for new features
fix for bug fixes
docs for documentation changes
style for formatting (no code change)
refactor for code restructuring without feature changes
test for adding or updating tests
chore for maintenance tasks (e.g., updating dependencies) 





To use CircleCI, a continuous integration and delivery platform, follow these steps:

Sign Up for CircleCI:

Create an account on CircleCI using GitHub, Bitbucket, or email.
Add Your Project:

After signing in, authorize CircleCI to access your repositories. Select the project you want to build and integrate with CircleCI.
Set Up CircleCI Config File:

In your project repository, create a .circleci folder in the root directory.
Inside this folder, create a config.yml file to define your build process.
Here's a basic example for a Node.js project:


version: 2.1
jobs:
  build:
    docker:
      - image: circleci/node:14
    steps:
      - checkout
      - run: npm install
      - run: npm test
workflows:
  version: 2
  build:
    jobs:
      - build


      
Customize the config file according to your project needs.
Push Your Code:

Commit the .circleci/config.yml file and push it to your repository. CircleCI will detect the changes and start building your project.
View Build Results:

You can monitor build progress and results on the CircleCI dashboard.
Add Test/Deployment Steps:

Modify the config.yml to include steps for running tests, building the app, or deploying to a server.
Would you like help with a specific part of the setup, like adding environment variables or integrating a specific service?


illustration 
https://popsy.co/illustrations/



