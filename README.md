# 🚀 Pac-Man on Amazon EKS with CI/CD

Deploying a Pac-Man application to Amazon EKS using Kubernetes, Docker, Amazon ECR, Amazon EBS and GitHub Actions.

---

## 📖 Project Overview

This project demonstrates a complete cloud-native deployment pipeline.

The application is containerized with Docker, stored in Amazon ECR, deployed to Amazon EKS, exposed through an AWS Network Load Balancer, and automatically updated using GitHub Actions.

---

## 🏗️ Architecture

```
Developer
    │
 git push
    ▼
GitHub Repository
    ▼
GitHub Actions
    ├────────► Amazon ECR
    │
    └────────► Amazon EKS
                     │
          ┌──────────┴──────────┐
          │                     │
     Pac-Man Deployment   MongoDB StatefulSet
          │                     │
      Pac-Man Pod              PVC
          │                     │
       Service             Amazon EBS
          │
AWS Network Load Balancer
          │
       Browser
```

Architecture diagram:

```
diagrams/architecture.png
```

---

## ☁️ Technologies

- Amazon EKS
- Amazon ECR
- Amazon EBS
- AWS Network Load Balancer
- Docker
- Kubernetes
- MongoDB
- GitHub Actions
- eksctl
- kubectl

---

## 📁 Project Structure

```
.
├── .github/
│   └── workflows/
├── diagrams/
├── infra/
├── k8s/
├── Dockerfile
├── README.md
└── ...
```

---

## ⚙️ Kubernetes Resources

| Resource | Purpose |
|----------|---------|
| Deployment | Pac-Man application |
| StatefulSet | MongoDB |
| PVC | Persistent storage |
| Service | Internal networking |
| LoadBalancer | Public access |

---

## 🚀 CI/CD Pipeline

Every push to the repository automatically:

- Builds Docker image
- Pushes image to Amazon ECR
- Connects to Amazon EKS
- Restarts the deployment

---

## 🌍 Application

The application is exposed through an AWS Network Load Balancer.

```
Browser
        │
        ▼
AWS NLB
        ▼
Pac-Man Service
        ▼
Pac-Man Pod
```

---

## 📸 Screenshots

Screenshots can be found in:

```
screenshots/
```

---

## 👨‍💻 Author

Nikita Stasevich
