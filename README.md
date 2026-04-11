# React Password Generator

A simple **React.js** application for generating secure passwords, published as a **sample deployment project for [Nife.io](https://nife.io)**.

This repository demonstrates how to run a lightweight frontend application locally, package it with Docker, and deploy it using [Nife.io](https://nife.io). It is intended as a practical sample for testing frontend deployment workflows and showcasing a simple React deployment path on Nife.io.

## Why this repository exists

This project is designed as a **deployment sample** as much as an application demo. The password generator itself is intentionally lightweight, which makes it useful for validating local development, containerization, CI/CD, and deployment workflows without the overhead of a large codebase.

If you want a small frontend app to test deployment on [Nife.io](https://nife.io), this repository is a good starting point.

## Features

| Feature | Description |
| --- | --- |
| Password generation | Generates a random password instantly |
| Length control | Lets users choose a password length between 8 and 26 characters |
| Character options | Supports uppercase letters, lowercase letters, numbers, and symbols |
| Clipboard copy | Allows copying the generated password directly from the UI |
| Toast notifications | Displays success and validation messages during use |
| Deployment-ready structure | Includes Docker, Nife configuration, and deployment workflow support |

## Tech Stack

| Technology | Purpose |
| --- | --- |
| React.js | Frontend framework |
| JavaScript (ES6+) | Application logic |
| HTML5 and CSS3 | User interface and styling |
| React Toastify | UI notifications |
| Docker | Containerized packaging |
| Nife.io | Deployment platform |
| GitHub Actions | Automated deployment workflow |

## Getting Started

### Prerequisites

For local development, install **Git**, **Node.js**, and **npm**. Because this project uses an older React Scripts setup, **Node.js 16** is the safest option for local compatibility.

### Clone the repository

```bash
git clone https://github.com/nifetency/react_password_generator.git
cd react_password_generator
```

### Install dependencies

```bash
npm install
```

### Start the development server

```bash
npm start
```

### Open the application

```text
http://localhost:3000
```

## Available Scripts

| Script | Description |
| --- | --- |
| `npm start` | Starts the development server |
| `npm run build` | Creates a production build |
| `npm test` | Runs the test runner |
| `npm run eject` | Ejects the Create React App configuration |

## Run with Docker

This repository includes a Dockerfile for containerized execution.

### Build the Docker image

```bash
docker build -t react-password-generator .
```

### Run the container

```bash
docker run -p 3000:3000 react-password-generator
```

After the container starts, open the app at `http://localhost:3000`.

## Deploy on Nife.io

You can deploy this application on [Nife.io](https://nife.io) using either the web console, a Docker image, the source repository, or the CLI.

### Option 1: Deploy from a Docker image

First, build and push the image to your preferred container registry.

```bash
docker build -t react-password-generator .
docker tag react-password-generator <username>/react-password-generator:latest
docker push <username>/react-password-generator:latest
```

Then create a new application in Nife.io with the following settings.

| Setting | Value |
| --- | --- |
| Source | Docker Image |
| Image | `<username>/react-password-generator:latest` |
| Internal Port | `3000` |
| External Port | `80` |
| Suggested Replicas | `1` |

### Option 2: Deploy from the Git repository

You can also deploy the project directly from GitHub through [Nife.io](https://nife.io).

| Setting | Value |
| --- | --- |
| Source | Git Repository |
| Provider | GitHub |
| Branch | `main` |
| Internal Port | `3000` |
| External Port | `80` |
| Build Mode | Auto-Dockerize with runtime |

### Option 3: Deploy with `nifectl`

If you prefer the command line, use the following workflow.

```bash
nifectl auth login
nifectl init
nifectl deploy
```

During initialization, select the repository source, choose GitHub as the provider, and use the `main` branch.

For step-by-step instructions, see the [Nife.io Quick Deploy documentation](https://docs.nife.io/overview/quick-deploy) and the [nifectl quick start guide](https://docs.nife.io/Quick-Start/Nifectl).

## Deployment Configuration Summary

This repository already includes a `nife.toml` file with deployment settings.

| Setting | Value |
| --- | --- |
| Internal service port | `3000` |
| Public ports | `80`, `443` |
| Request CPU | `250m` |
| Request memory | `512Mi` |
| Limit CPU | `500m` |
| Limit memory | `1Gi` |
| Routing policy | `latency` |
| Auto rollback | Enabled |

## Continuous Deployment

The repository includes a GitHub Actions workflow that triggers deployment on pushes to the `main` and `master` branches.

To use that workflow, configure the following repository secret.

| Secret | Purpose |
| --- | --- |
| `NIFE_ACCESS_TOKEN` | Authenticates automated deployment to Nife.io |

## Repository Structure

| Path | Purpose |
| --- | --- |
| `src/` | React application source code |
| `public/` | Static public assets |
| `build/` | Production build output |
| `.github/workflows/` | Deployment automation workflow |
| `Dockerfile` | Container build instructions |
| `nife.toml` | Nife deployment configuration |
| `package.json` | Project metadata, scripts, and dependencies |

## Environment Variables

| Variable | Description | Default |
| --- | --- | --- |
| `PORT` | Local application port | `3000` |

## Troubleshooting

| Issue | Suggested fix |
| --- | --- |
| Dependencies fail to install | Confirm that Node.js and npm are installed correctly |
| React app fails to start on newer Node versions | Try Node.js 16 for local development compatibility |
| Port `3000` is already in use | Stop the conflicting process or change the local port mapping |
| Docker build fails | Rebuild the image after checking the Dockerfile and dependencies |
| Deployment cannot pull the image | Ensure that the image exists and is accessible in the registry |
| App loads with a blank screen | Check browser console errors and deployment logs |


## Acknowledgements

This project is based on the original [`react_password_generator`](https://github.com/Megh2507/react_password_generator) repository by [@Megh2507](https://github.com/Megh2507).

This version has been adapted and documented as a sample deployment project for [Nife.io](https://nife.io).

## License

This project is licensed under the **MIT License**. Please add the `LICENSE` file to the repository root so the license is displayed correctly on GitHub.

## References

[1]: https://nife.io "Nife.io"
[2]: https://docs.nife.io/overview/quick-deploy "Nife.io Quick Deploy"
[3]: https://docs.nife.io/Quick-Start/Nifectl "Nifectl Quick Start"
[4]: https://github.com/nifetency/react_password_generator "nifetency/react_password_generator"
[5]: https://github.com/Megh2507/react_password_generator "Original react_password_generator repository"


live
