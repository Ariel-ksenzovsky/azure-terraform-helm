# Azure Terraform Helm

## Overview

This project provides Infrastructure as Code (IaC) for deploying resources on Microsoft Azure using Terraform and Helm. It automates the provisioning and management of cloud infrastructure, ensuring consistency and scalability.

## Features

- **Terraform**: Infrastructure provisioning on Azure
- **Helm**: Kubernetes package management
- **Azure Kubernetes Service (AKS)**: Deploy and manage Kubernetes clusters
- **Azure Resources**: VNET, RBAC, and more
- **AWS S3**: Storage solution for the project
- **CI/CD Integration**: Automate deployments using GitHub Actions

## Prerequisites

Before using this project, ensure you have the following installed:

- [Terraform](https://developer.hashicorp.com/terraform/downloads)
- [Helm](https://helm.sh/docs/intro/install/)
- [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli)
- [Kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- [AWS CLI](https://aws.amazon.com/cli/) (for managing S3 storage)
- An active [Azure subscription](https://portal.azure.com/)
- An active [AWS account](https://aws.amazon.com/)

## Setup & Deployment

### 1. Clone the Repository

```bash
git clone https://github.com/Ariel-ksenzovsky/azure-terraform-helm.git
cd azure-terraform-helm
```

### 2. Authenticate with Azure

```bash
az login
az account set --subscription <SUBSCRIPTION_ID>
```

### 3. Authenticate with AWS

```bash
aws configure
```

### 4. Initialize Terraform

```bash
terraform init
```

### 5. Apply Terraform Configuration

```bash
terraform apply -auto-approve
```

### 6. Configure Kubernetes with Helm

```bash
kubectl config use-context <AKS_CLUSTER>
helm install my-app ./helm-chart
```

## Project Structure

```
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
```

## CI/CD Pipeline

This project includes GitHub Actions workflows for automating infrastructure deployment. The pipeline consists of the following stages:

### **Continuous Integration (CI)**
1. Build the container image
2. Push the image to a container registry

### **Continuous Deployment (CD)**
1. Run Terraform plan & apply to configure infrastructure
2. Build the Helm chart
3. Deploy the application to AKS using Helm
4. Ensure proper configuration and monitoring

## Cleanup

To remove the deployed resources, run:

```bash
terraform destroy -auto-approve
```

## Contribution

Contributions are welcome! Please open an issue or pull request for suggestions and improvements.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author

[Ariel Ksenzovsky](https://github.com/Ariel-ksenzovsky)

