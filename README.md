# CloudShop E-Commerce Platform

## Project Overview
CloudShop is a cloud-native e-commerce DevOps project designed to demonstrate modern CI/CD automation, Docker containerization, Git Flow collaboration, Kubernetes configuration, and cloud deployment practices. The project simulates an enterprise-level deployment pipeline using GitHub Actions, Docker, Jenkins, Kubernetes manifests, and Render cloud deployment services.

The platform consists of multiple microservices:
- User Service
- Product Service
- Order Service
- Notification Service
- Frontend Dashboard

---

# Technologies Used

- HTML5
- CSS3
- Git & GitHub
- GitHub Actions
- Docker
- Docker Hub
- Jenkins
- Kubernetes
- Render Cloud Platform
- GitHub Environments

---

# Repository Structure

```bash
.github/
│
├── workflows/
│   ├── ci.yml
│   └── cd.yml
│
k8s/
│   ├── frontend-deployment.yaml
│   ├── user-deployment.yaml
│   ├── product-deployment.yaml
│   ├── order-deployment.yaml
│   ├── notification-deployment.yaml
│   ├── configmap.yaml
│   ├── secret.yaml
│   └── autoscaler.yaml
│
src/
│   ├── frontend/
│   ├── user-service/
│   ├── product-service/
│   ├── order-service/
│   └── notification-service/
│
Dockerfile
Jenkinsfile
README.md
```

---

# Git Flow Strategy

The project follows Git Flow branching methodology:

* `develop` → Development environment
* `release` → Staging/QA environment
* `production` → Production environment
* `feature/*` → Feature branches for development tasks

Branch promotion workflow:

```text
feature branch → develop → release → production
```

Protected production deployments and pull request workflows were implemented to simulate enterprise DevOps practices.

---

# Docker Containerization

The frontend application was containerized using Docker and deployed using an Nginx Alpine image.

## Docker Features

* Dockerized frontend application
* Semantic image versioning
* Docker image pushed to Docker Hub
* Local container execution and testing

## Docker Hub Repository

[https://hub.docker.com/repository/docker/mujtaba72/cloudshop-frontend/general](https://hub.docker.com/repository/docker/mujtaba72/cloudshop-frontend/general)

---

# CI Pipeline (GitHub Actions)

A Continuous Integration (CI) pipeline was implemented using GitHub Actions.

## CI Features

* Automated workflow execution on branch pushes
* HTML linting validation
* CSS linting validation
* Automated Docker image build
* Branch-specific CI execution

The CI pipeline validates frontend code quality and ensures Docker builds succeed before deployment.

---

# CD Pipeline (GitHub Actions + Render)

Continuous Deployment (CD) workflows were implemented for separate deployment environments.

## CD Features

* Development deployment pipeline
* Staging deployment pipeline
* Production deployment pipeline
* Branch-based automatic deployment
* Environment-based deployment approvals
* Protected production deployment reviews

Render services were configured for automated deployments.

---

# Kubernetes Configuration

Kubernetes deployment manifests were created for all project services.

## Kubernetes Components

* Frontend Deployment
* User Service Deployment
* Product Service Deployment
* Order Service Deployment
* Notification Service Deployment
* ConfigMap
* Secret
* Horizontal Pod Autoscaler

## Kubernetes Features

* Rolling update deployment strategy
* LoadBalancer service configuration
* Environment configuration using ConfigMaps
* Secret management
* Autoscaling configuration

---

# Jenkins Pipeline

A declarative Jenkins pipeline was created to simulate enterprise CI/CD workflows.

## Jenkins Stages

* Checkout
* Build
* Test
* Docker Build
* Docker Push
* Deploy
* Notify

The Jenkinsfile demonstrates enterprise DevOps automation pipeline design.

---

# Live Deployment Links

## Development Environment

[https://develop-university-cs-dept-devop-pipeline.onrender.com](https://develop-university-cs-dept-devop-pipeline.onrender.com)

## Staging / QA Environment

[https://cloudshop-staging-release.onrender.com](https://cloudshop-staging-release.onrender.com)

## Production Environment

[https://cloudshop-production.onrender.com](https://cloudshop-production.onrender.com)

---

# GitHub Repository

[https://github.com/muhammad-mujtaba-haider-naqvi/university-cs-dept-devop-pipeline](https://github.com/muhammad-mujtaba-haider-naqvi/university-cs-dept-devop-pipeline)

---

# Team Collaboration

The project demonstrates collaborative DevOps workflow practices through:

* Git Flow branching
* Pull requests
* Branch protection rules
* Multiple contributors
* Feature branch development
* Environment approvals
* CI/CD automation

---

# Learning Outcomes

Through this project, the following DevOps concepts were learned and implemented:

* Git Flow and collaborative GitHub workflows
* Docker containerization and image management
* CI/CD automation using GitHub Actions
* Cloud deployment using Render
* Kubernetes deployment configuration
* Environment secret management
* Branch protection and deployment approvals
* Enterprise DevOps pipeline simulation using Jenkins

This project provided practical experience in building a scalable cloud-native DevOps workflow from development to production deployment.
