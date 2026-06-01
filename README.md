# Terraform EKS NodeJS MongoDB Project

Infrastructure-as-Code project that provisions an AWS EKS cluster using Terraform and deploys a NodeJS application connected to MongoDB using Helm charts.

The project demonstrates cloud infrastructure provisioning, Kubernetes orchestration, and application deployment using modern DevOps practices.

## Tech Stack

- AWS EKS
- Terraform
- Kubernetes
- Helm
- Docker
- NodeJS
- MongoDB

## Project Overview

This project demonstrates how to deploy a containerized web application to AWS EKS.

The infrastructure is managed with Terraform, while the application and database are deployed to Kubernetes using Helm charts.

## Architecture

```text
User
  │
  ▼
AWS LoadBalancer
  │
  ▼
NodeJS Service
  │
  ▼
NodeJS Pods
  │
  ▼
MongoDB Service
  │
  ▼
MongoDB Pod
```

## Repository Structure

```text
terraform/     Terraform infrastructure files
helm/          Helm charts for NodeJS and MongoDB
nodejs/        NodeJS application source code
```

## What This Project Demonstrates

- Creating cloud infrastructure with Terraform
- Provisioning an EKS Kubernetes cluster
- Deploying applications using Helm
- Running NodeJS and MongoDB in Kubernetes
- Exposing an application using a Kubernetes LoadBalancer
- Managing application configuration with Helm values

## Deployment Steps

### Provision Infrastructure

```bash
cd terraform
terraform init
terraform plan
terraform apply
```

### Configure kubectl

```bash
aws eks update-kubeconfig --region <region> --name <cluster-name>
```

### Verify Deployment

```bash
kubectl get pods
kubectl get svc
```

## Project Goals

This project was built to gain hands-on experience with:

- Infrastructure as Code (IaC)
- Kubernetes orchestration
- Helm package management
- AWS cloud infrastructure
- Containerized application deployment

## Future Improvements

- Horizontal Pod Autoscaling (HPA)
- Monitoring with Prometheus and Grafana
- Ingress Controller configuration
- GitHub Actions CI/CD pipeline
- Multi-environment deployments (dev/staging/prod)


