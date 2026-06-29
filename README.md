# 🚀 React Docker CI/CD Pipeline

A production-style DevOps project demonstrating the complete software delivery lifecycle for a React application using **Docker**, **GitHub Actions**, and **AWS**.

The project implements a complete **Continuous Integration (CI)** and **Continuous Deployment (CD)** pipeline that automatically:

* Builds the application
* Runs tests inside Docker
* Creates a deployment artifact
* Uploads the artifact to Amazon S3
* Deploys the application to an AWS EC2 instance
* Runs the production application inside a Docker container using Docker Compose

---

# 📖 Project Overview

This project demonstrates modern DevOps practices by separating the application into two environments:

* **Development Environment**

  * Dockerfile.dev
  * Docker Compose (Development)
  * Hot Reload
  * Dockerized Testing

* **Production Environment**

  * Production Dockerfile
  * Docker Compose (Production)
  * Nginx Container
  * Automated Deployment via GitHub Actions

---

# 🏗️ Architecture

![Architecture](images/architecture.png)

---

# ⚙️ Technologies Used

* React
* Docker
* Docker Compose
* GitHub Actions
* Jenkins
* Amazon EC2
* Amazon S3
* AWS IAM
* AWS CLI
* Ubuntu Server
* Nginx
* Node.js

---

# 📂 Project Structure

```text
.
├── .github/
│   └── workflows/
│       └── deploy.yml
├── build/
├── public/
├── src/
├── Dockerfile
├── Dockerfile.dev
├── docker-compose.dev.yml
├── docker-compose.prod.yml
├── package.json
├── package-lock.json
├── README.md
└── images/
```

---

# 💻 Development Environment

The development environment uses:

* Dockerfile.dev
* docker-compose.dev.yml

Features:

* Live Reload
* Bind Mounts
* Dockerized React Development Server
* Dockerized Testing

Start the development environment:

```bash
docker compose -f docker-compose.dev.yml up
```

---

# 🚀 Production Environment

The production deployment uses:

* Dockerfile
* docker-compose.prod.yml

The React application is built by GitHub Actions.

The production Docker image contains only:

* Nginx
* React production build

No Node.js runtime exists inside the production container.

---

# 🔄 CI/CD Pipeline

## Continuous Integration

Two CI solutions were implemented during this project:

### Jenkins (Local CI)

The Jenkins pipeline demonstrates local CI by:

1. Building the development Docker image
2. Running React tests inside Docker

### GitHub Actions (Cloud CI)

GitHub Actions performs:

1. Checkout Repository
2. Build Development Docker Image
3. Run React Tests inside Docker
4. Install Dependencies
5. Build Production React Files
6. Create Deployment Artifact

## Continuous Deployment

After a successful build:

1. Configure AWS Credentials
2. Upload Deployment Artifact to Amazon S3
3. SSH into AWS EC2
4. Download Deployment Artifact
5. Extract Deployment Package
6. Build Production Docker Image
7. Deploy using Docker Compose
8. Launch the Nginx Container

---

# ☁️ AWS Infrastructure

AWS Services used:

* Amazon EC2
* Amazon S3
* AWS IAM

The EC2 instance uses an **IAM Role** to securely access Amazon S3 without storing AWS credentials on the server.

GitHub Actions authenticates to AWS using GitHub Secrets.

---

# 📦 Deployment Artifact

GitHub Actions generates the deployment artifact:

```text
deploy.zip
│
├── build/
├── Dockerfile
└── docker-compose.prod.yml
```

The EC2 instance downloads the artifact from Amazon S3 and builds the production Docker image locally.

---

# 🐳 Docker Overview

## Development

* Dockerfile.dev
* Docker Compose Development
* React Development Server
* Dockerized Testing

## Production

* Dockerfile
* Docker Compose Production
* Nginx Container
* React Production Build

---

# 📸 Project Screenshots

## Architecture

![Architecture](images/architecture.png)

---

## Local React Application

![Local React Application](images/react-local.png)

---

## Docker Images

Shows the development and production Docker images.

![Docker Images](images/docker-images.png)

---

## Docker Compose (Development)

Development environment running with Docker Compose.

![Docker Compose Development](images/docker-compose-dev.png)

---

## GitHub Repository

Repository structure and project files.

![GitHub Repository](images/github-repository.png)

---

## GitHub Actions CI/CD Pipeline

Successful CI/CD workflow execution.

![GitHub Actions](images/github-actions.png)

---

## Jenkins Pipeline

Successful Jenkins build running locally.

![Jenkins Pipeline](images/jenkins-pipeline.png)

---

## Amazon S3 Deployment Artifact

Deployment artifact uploaded successfully.

![S3 Artifact](images/s3-artifact.png)

---

## AWS EC2 Instance

Running Ubuntu EC2 instance.

![EC2 Dashboard](images/ec2-dashboard.png)

---

## Security Group Configuration

Inbound rules allowing SSH and HTTP traffic.

![Security Group](images/security-group.png)

---

## IAM Role

EC2 IAM Role with Amazon S3 permissions.

![IAM Role](images/iam-role.png)

---

## Docker Running on EC2

Production container running on the EC2 instance.

![Docker on EC2](images/ec2-docker.png)

---

## Docker Compose on EC2

Docker Compose managing the production deployment.

![Docker Compose EC2](images/ec2-compose.png)

---

## Deployment Success

Successful deployment logs from GitHub Actions.

![Deployment Success](images/deployment-success.png)

---

## Production Website

React application running from the AWS EC2 Public IP.

![Production Website](images/aws-react-app.png)

---

# 🎯 Learning Outcomes

This project demonstrates:

* Dockerizing React Applications
* Multi-Stage Docker Workflow
* Docker Compose
* GitHub Actions CI/CD
* Jenkins Pipelines CI
* Automated Testing
* Deployment Artifacts
* Amazon S3
* Amazon EC2
* AWS IAM Roles
* AWS CLI
* SSH Automation
* Containerized Production Deployment
* Nginx Web Server
* Infrastructure Automation

---

# 🔮 Future Improvements

* GitHub OIDC Authentication
* Docker Hub Deployment Strategy
* Terraform Infrastructure as Code
* Kubernetes Deployment
* HTTPS with Let's Encrypt
* Custom Domain with Route 53
* Blue/Green Deployment Strategy

---

# 👨‍💻 Author

**Moaz Mohamed**

DevOps Portfolio Project
