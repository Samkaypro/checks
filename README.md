# [Samkaypro](https://x.com/samkaypro) Development Best Practices

This README outlines development best practices, including code checks, useful libraries, and CI/CD setup.

## Table of Contents
- [Code Checks](#code-checks)
  - [Type Checking](#type-checking)
  - [ESLint](#eslint)
  - [Prettier (Code Formatting)](#prettier-code-formatting)
  - [Unit Tests](#unit-tests)
  - [Husky (Git Hooks)](#husky-git-hooks)
- [Useful Libraries](#useful-libraries)
- [Commit Message Guidelines](#commit-message-guidelines)
- [CircleCI Setup](#circleci-setup)

## Code Checks

### Type Checking

To perform a type check in a TypeScript project:

```bash
npx tsc --noEmit
```

The `--noEmit` flag tells TypeScript to perform a type check without generating any output files.

### ESLint

To check for ESLint errors:

```bash
npx eslint .
```

To automatically fix errors that ESLint can correct:

```bash
npx eslint . --fix
```

Alternatively, if you have a script in your `package.json`:

```bash
npm run lint
```

### Prettier (Code Formatting)

To format your entire codebase:

```bash
npx prettier --write .
```

### Unit Tests

Run tests using:

```bash
npm test
```

### Husky (Git Hooks)

Install Husky:

```bash
npx husky-init && npm install
```

Add a pre-commit hook:

```bash
npx husky set .husky/pre-commit "npm run lint && npm test"
```

## Useful Libraries

1. Icon Libraries
   - [Lucide](https://lucide.dev/)

2. Illustration Libraries
   - [unDraw](https://undraw.co/)
   - [Popsy](https://popsy.co/illustrations)

3. Domain Search
   - [OSINT.SH](https://osint.sh/)

## Commit Message Guidelines

Use consistent commit types:

- `feat`: New features
- `fix`: Bug fixes
- `docs`: Documentation changes
- `style`: Formatting (no code change)
- `refactor`: Code restructuring without feature changes
- `test`: Adding or updating tests
- `chore`: Maintenance tasks (e.g., updating dependencies)

## CircleCI Setup

1. Sign up for CircleCI using GitHub, Bitbucket, or email.
2. Add your project in the CircleCI dashboard.
3. Create a `.circleci/config.yml` file in your project root:

```yaml
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
```

4. Customize the config file according to your project needs.
5. Commit and push the `.circleci/config.yml` file.
6. Monitor build progress and results on the CircleCI dashboard.
7. Modify the `config.yml` to include steps for running tests, building the app, or deploying to a server.

For more detailed instructions or help with specific setup tasks, please refer to the [CircleCI documentation](https://circleci.com/docs/).






