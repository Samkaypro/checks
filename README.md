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












..........
.........
........
.......
......
.....
....


1. Install Docker
For Windows:
Download Docker Desktop:

Visit the Docker Desktop for Windows page.
Download the installer.
Install Docker Desktop:

Run the installer.
Follow the installation instructions, which may include enabling WSL 2 and the virtualization feature in BIOS.
Start Docker:

After installation, launch Docker Desktop from your Start menu.
Sign in to Docker Hub (Optional):

Create an account on Docker Hub or sign in if you already have an account.
For macOS:
Download Docker Desktop:

Go to the Docker Desktop for Mac page.
Download the installer.
Install Docker Desktop:

Open the downloaded .dmg file.
Drag and drop Docker into the Applications folder.
Start Docker:

Open Docker from your Applications folder.
You may be prompted to authorize Docker to run.
Sign in to Docker Hub (Optional):

Create an account on Docker Hub or sign in if you already have an account.
For Linux:
Update your package index:

bash
Copy code
sudo apt-get update
Install required packages:

bash
Copy code
sudo apt-get install apt-transport-https ca-certificates curl software-properties-common
Add Docker’s official GPG key:

bash
Copy code
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
Set up the stable repository:

bash
Copy code
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
Install Docker:

bash
Copy code
sudo apt-get update
sudo apt-get install docker-ce
Verify Docker installation:

bash
Copy code
sudo systemctl status docker
(Optional) Manage Docker as a non-root user:

Create the docker group and add your user:
bash
Copy code
sudo groupadd docker
sudo usermod -aG docker $USER
Log out and log back in for the group change to take effect.
2. Verify Docker Installation
After installation, you can verify that Docker is installed correctly:

Open a terminal or command prompt.

Run the following command:

bash
Copy code
docker --version
Run the Docker Hello World container:

bash
Copy code
docker run hello-world
This command downloads a test image and runs it in a container. If everything is set up correctly, you should see a success message.
3. Basic Docker Commands
List Docker images:

bash
Copy code
docker images
List running containers:

bash
Copy code
docker ps
List all containers (running and stopped):

bash
Copy code
docker ps -a
Run a container in interactive mode:

bash
Copy code
docker run -it <image-name> /bin/bash
Stop a running container:

bash
Copy code
docker stop <container-id>
Remove a container:

bash
Copy code
docker rm <container-id>
Remove an image:

bash
Copy code
docker rmi <image-id>
4. Further Learning
Once you're comfortable with the basics, consider exploring more advanced topics like Docker Compose, networking, and Dockerfile creation for building custom images.