# CNO Project – CloudOps Dashboard

A simple web-based CloudOps Dashboard developed using HTML and CSS, containerized with Docker, and deployed using Kubernetes (Minikube).

This project demonstrates containerization, Kubernetes orchestration, and CI/CD automation using Jenkins and GitHub.

## 🚀 Technologies Used

- **HTML5** – Website structure
- **CSS3** – Website styling
- **Docker** – Application containerization
- **Kubernetes** – Container orchestration
- **Minikube** – Local Kubernetes cluster
- **kubectl** – Kubernetes cluster management
- **Jenkins** – CI/CD pipeline automation
- **Git & GitHub** – Source code management
- **GitHub Pages** – Static website hosting

## 📁 Project Structure

```text
lab1-docker-kubernetes/
│
├── index.html
├── dockerfile
├── deployment.yaml
├── service.yaml
├── Jenkinsfile
└── readme.md
```

## 🐳 Docker Implementation

The application is containerized using Docker.

### Build Docker Image

```bash
docker build -t cloudops-dashboard:v1 -f dockerfile .
```

### View Docker Images

```bash
docker images
```

## ☸️ Kubernetes Deployment

The application is deployed to a local Kubernetes cluster using Minikube.

### Start Minikube

```bash
minikube start
```

### Check Cluster Status

```bash
minikube status
kubectl get nodes
```

### Deploy Application

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

### Verify Deployment

```bash
kubectl get deployments
kubectl get pods
kubectl get services
```

### Kubernetes Configuration

The deployment configuration includes:

| Configuration | Value |
|---|---|
| Deployment Name | cloudops-deployment |
| Replicas | 2 |
| Container Name | cloudops-container |
| Docker Image | cloudops-dashboard:v1 |
| Container Port | 80 |
| Image Pull Policy | Never |

## 🔄 CI/CD Pipeline Using Jenkins

Jenkins is used to automate the build and deployment process.

The Jenkins pipeline connects to the GitHub repository and automates the application deployment using Docker and Kubernetes.

### Pipeline Stages

1. **Checkout Code:** Fetches the latest source code from GitHub.
2. **Build Docker Image:** Builds the application Docker image.
3. **Load Image into Minikube:** Makes the Docker image available inside the Minikube cluster.
4. **Deploy to Kubernetes:** Applies the Kubernetes deployment and service configurations.
5. **Verify Deployment:** Checks deployment status, pods, and services.

### Jenkins Pipeline Commands

```bash
docker build -t cloudops-dashboard:v1 -f dockerfile .
```

```bash
minikube image load cloudops-dashboard:v1
```

```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
```

## 🌐 GitHub Repository

Source code:

https://github.com/Ni616-hajbe/CNO-PROJECT-

## 🌍 GitHub Pages

The static HTML/CSS website can also be hosted using GitHub Pages.

## 🎯 Project Objectives

- Understand Docker containerization.
- Deploy applications using Kubernetes.
- Manage containers using Minikube and kubectl.
- Automate application deployment using Jenkins.
- Understand Continuous Integration and Continuous Deployment (CI/CD).
- Integrate GitHub with Jenkins for source code management.

## 👩‍💻 Author

**Ni616-hajbe**

GitHub: https://github.com/Ni616-hajbe

---

*This project demonstrates practical implementation of frontend development, containerization, Kubernetes orchestration, and DevOps CI/CD practices.*