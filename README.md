# Azure Terraform Helm

Overview

This project provides Infrastructure as Code (IaC) for deploying resources on Microsoft Azure using Terraform and Helm. It automates the provisioning and management of cloud infrastructure, ensuring consistency and scalability.

Features

Terraform: Infrastructure provisioning on Azure

Helm: Kubernetes package management

Azure Kubernetes Service (AKS): Deploy and manage Kubernetes clusters

Azure Resources: VNET, RBAC, and more

AWS S3: Storage solution for the project

CI/CD Integration: Automate deployments using GitHub Actions

Prerequisites

Before using this project, ensure you have the following installed:

Terraform

Helm

Azure CLI

Kubectl

AWS CLI (for managing S3 storage)

An active Azure subscription

An active AWS account

Setup & Deployment

1. Clone the Repository

git clone https://github.com/Ariel-ksenzovsky/azure-terraform-helm.git
cd azure-terraform-helm

2. Authenticate with Azure

az login
az account set --subscription <SUBSCRIPTION_ID>

3. Authenticate with AWS

aws configure

4. Initialize Terraform

terraform init

5. Apply Terraform Configuration

terraform apply -auto-approve

6. Configure Kubernetes with Helm

kubectl config use-context <AKS_CLUSTER>
helm install my-app ./helm-chart

Project Structure

.
├── terraform/          # Terraform configuration files
├── helm-chart/         # Helm chart for application deployment
├── .github/workflows/  # CI/CD pipeline definitions
├── app/
│   ├── app.py         # Main application file
│   ├── templates/     # HTML templates for the app
│   ├── static/        # Static files (CSS, JS, images)
│   ├── requirements.txt # Dependencies for the app
├── Dockerfile         # Docker configuration for the app
├── docker-compose.yml # Docker Compose configuration for local testing
├── README.md          # Project documentation
└── .gitignore         # Ignore unnecessary files

CI/CD Pipeline

This project includes GitHub Actions workflows for automating infrastructure deployment. The pipeline:

Builds the container image in the CI workflow

Runs Terraform plan & apply

Deploys Helm charts to AKS in the CD workflow

Ensures proper configuration and monitoring

Cleanup

To remove the deployed resources, run:

terraform destroy -auto-approve

Contribution

Contributions are welcome! Please open an issue or pull request for suggestions and improvements.
