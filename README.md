# Pac-Man EKS CI/CD Project

## Overview

This project deploys a Pac-Man Node.js application on Amazon EKS using Kubernetes, MongoDB, Amazon ECR, EBS Persistent Volumes, Network Load Balancer, and GitHub Actions CI/CD.

## Architecture

- Pac-Man application runs as a Kubernetes Deployment.
- MongoDB runs as a Kubernetes StatefulSet.
- MongoDB data is stored on an Amazon EBS Persistent Volume.
- The application is exposed using an AWS Network Load Balancer.
- Docker images are stored in Amazon ECR.
- GitHub Actions automatically builds, pushes, and deploys the application to EKS.

## Technologies

- AWS EKS
- EKS Auto Mode
- Docker
- Kubernetes
- MongoDB
- Amazon ECR
- Amazon EBS
- Network Load Balancer
- GitHub Actions
- eksctl
- kubectl

## Project Structure

```text
.
├── Dockerfile
├── infra/
│   └── cluster.yaml
├── k8s/
│   ├── storageclass.yaml
│   ├── mongo-service.yaml
│   ├── mongo-statefulset.yaml
│   ├── pacman-deployment.yaml
│   └── pacman-service.yaml
├── .github/
│   └── workflows/
│       └── deploy.yml
├── screenshots/
└── README.md
Deployment Flow
Developer pushes code to GitHub
        ↓
GitHub Actions starts
        ↓
Docker image is built
        ↓
Image is pushed to Amazon ECR
        ↓
GitHub Actions updates EKS deployment
        ↓
Pac-Man runs on EKS
Kubernetes Resources
MongoDB

MongoDB is deployed using a StatefulSet with a Persistent Volume Claim.

kubectl get statefulset
kubectl get pvc
Pac-Man Application

Pac-Man is deployed using a Kubernetes Deployment.

kubectl get deployment
kubectl get pods
Load Balancer

The application is exposed using a Kubernetes Service of type LoadBalancer.

kubectl get svc
CI/CD

GitHub Actions workflow:

.github/workflows/deploy.yml

The workflow performs:

Checkout repository
Configure AWS credentials
Login to Amazon ECR
Build Docker image
Push Docker image to ECR
Update kubeconfig
Restart Kubernetes deployment
Application URL
http://<AWS_NLB_DNS_NAME>
Screenshots

Screenshots are stored in the screenshots/ folder.
