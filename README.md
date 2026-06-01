# EKS Node.js MongoDB Terraform

End-to-end AWS infrastructure project using Terraform, Kubernetes, Helm, Docker, Node.js, and MongoDB.

## Overview

This project provisions an AWS EKS cluster using Terraform and deploys a containerized Node.js application connected to MongoDB.

The goal of this project is to demonstrate a complete cloud-native deployment workflow, from infrastructure provisioning to running an application on Kubernetes using Helm charts.


## Architecture

```text
Internet
    │
    ▼
AWS LoadBalancer
    │
    ▼
Node.js Service
    │
    ▼
Node.js Pod
    │
    ▼
MongoDB Service
    │
    ▼
MongoDB Pod
```

## What It Builds

- AWS networking for the EKS environment
- Amazon EKS cluster
- Kubernetes worker nodes
- Helm-based deployment for the Node.js application
- Helm-based deployment for MongoDB
- Kubernetes services for internal and external communication
- External access through a LoadBalancer service
- Application configuration for connecting Node.js to MongoDB

## Application

The application is a simple Node.js service connected to MongoDB.

It demonstrates communication between a backend application and a database running inside a Kubernetes cluster.

## Tech Stack

- AWS
- Terraform
- Amazon EKS
- Kubernetes
- Helm
- Docker
- Node.js
- MongoDB
- Linux
- Git

## Project Structure

```text
eks-nodejs-mongodb-terraform/
├── mongodb/
│   └── docker-entrypoint-initdb.d/
├── nodejs/
├── terraform/
│   ├── mongodb-helm-chart/
│   ├── nodejs-helm-chart/
│   ├── helm.tf
│   ├── main.tf
│   ├── outputs.tf
│   ├── variables.tf
│   └── .terraform.lock.hcl
├── .gitignore
└── README.md
```

## Setup

Clone the repository:

```bash
git clone https://github.com/IdanGrapie/eks-nodejs-mongodb-terraform.git
cd eks-nodejs-mongodb-terraform
```

Configure AWS credentials:

```bash
aws configure
```

Go to the Terraform directory:

```bash
cd terraform
```

Initialize Terraform:

```bash
terraform init
```

Review the planned changes:

```bash
terraform plan
```

Apply the infrastructure:

```bash
terraform apply
```

## Configure kubectl

After the EKS cluster is created, update your kubeconfig:

```bash
aws eks update-kubeconfig --region <aws-region> --name <cluster-name>
```

Verify the cluster:

```bash
kubectl get nodes
```

Check the deployed resources:

```bash
kubectl get pods
kubectl get services
```

## Access the Application

Find the external LoadBalancer address:

```bash
kubectl get svc
```

Open the LoadBalancer DNS address in your browser.

## Cleanup

To avoid unnecessary AWS costs, destroy the infrastructure when finished:

```bash
cd terraform
terraform destroy
```

## Notes

- This project is intended for learning and portfolio demonstration purposes.
- It is not configured as a production-ready deployment.
- Terraform state files should not be committed to GitHub.
- Secrets and credentials should never be pushed to the repository.
- AWS resources may generate costs while they are running.


## Future Improvements

- Add CI/CD for automated builds and deployments
- Add Kubernetes Ingress
- Add persistent storage for MongoDB
- Move secrets to Kubernetes Secrets or AWS Secrets Manager
- Add monitoring with Prometheus and Grafana
- Add GitOps deployment with ArgoCD
- Add a clearer architecture diagram

