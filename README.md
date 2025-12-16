# Microservices Deployment on AWS EKS with Jenkins Multibranch Pipeline

## 📌 Overview
Deployed a microservices application on AWS EKS using Jenkins Multibranch Pipeline. Implemented namespace isolation, RBAC, and secure credential management. The **main branch** contains a Jenkinsfile that applies all Kubernetes manifests (`kubectl apply`) for deployments and services, ensuring centralized orchestration.

<img width="1920" height="1080" alt="New Project" src="https://github.com/user-attachments/assets/b7dda395-d041-446a-8915-fe59e6aa556a" />


## 🚀 Tech Stack
- AWS EKS
- Jenkins (Multibranch Pipeline, Kubernetes, Docker Pipeline, Kubernetes CLI plugins)
- Docker & DockerHub
- Kubernetes (Namespaces, Deployments, Services, RBAC)
- Secrets & Jenkins Credential Manager

## ⚙️ Implementation Details
- **Namespace Isolation**: All resources deployed in `webapps` namespace.
- **RBAC Security**: Created `jenkins` ServiceAccount, Role, and RoleBinding scoped to `webapps`.
- **Secrets Management**: DockerHub credentials and Kubernetes token stored securely in Jenkins Credential Manager.
- **Pipeline Flow**:
  1. Developer commits code → GitHub
  2. Jenkins Multibranch Pipeline triggers
  3. Builds Docker images using Dockerfile (per service)
  4. Tags & pushes images to DockerHub
  5. **Main branch Jenkinsfile applies all manifests (`kubectl apply`)** for deployments and services
  6. Deploys microservices into `webapps` namespace on EKS

## ✅ Outcome
Delivered a secure, scalable, production-ready CI/CD pipeline for microservices deployment with centralized orchestration.
