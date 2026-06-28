# React Docker Pipeline

A sample React application used to demonstrate modern DevOps practices including Docker, Docker Compose, GitHub Actions Continuous Integration (CI), and Docker-based deployment workflows.

## Technologies

* React
* Docker
* Docker Compose
* GitHub Actions
* Nginx
* Node.js

## Project Structure

```text
.
├── .github/
│   └── workflows/
│       └── deploy.yml
├── Dockerfile
├── Dockerfile.dev
├── docker-compose.yml
├── package.json
└── src/
```

## Development

### Install dependencies

```bash
npm install
```

### Start the development server

```bash
npm run start
```

The application will be available at:

```text
http://localhost:3000
```

## Testing

Run the React test suite:

```bash
npm run test
```

The GitHub Actions CI pipeline executes the tests automatically inside a Docker container.

## Production Build

Generate the optimized production build:

```bash
npm run build
```

The production build is placed inside the `build/` directory.

## Docker

### Build the development image

```bash
docker build -t react-lab:v1 -f Dockerfile.dev .
```

### Build the production image

```bash
docker build -t react-lab:prod .
```

## Docker Compose

Start the development environment:

```bash
docker compose up
```

Stop the environment:

```bash
docker compose down
```

## Continuous Integration (CI)

The project uses GitHub Actions to automate Continuous Integration.

Current pipeline:

* Checkout repository
* Build Docker development image
* Run React tests inside a Docker container

The workflow is located at:

```text
.github/workflows/deploy.yml
```

> This workflow currently implements the CI stage. Deployment (CD) will be added in a later phase.

## Continuous Deployment (Planned)

The next phase of the project will include:

* Build production Docker image
* Push image to Docker Hub
* Deploy to an AWS EC2 instance
* Automatically update the running Docker container

## Learning Objectives

This project demonstrates:

* Containerizing React applications
* Multi-stage Docker builds
* Docker Compose for development
* Bind mounts and Docker volumes
* React testing inside Docker containers
* GitHub Actions CI pipelines
* Production-ready Docker images using Nginx

