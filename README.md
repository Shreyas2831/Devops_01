# Automated Flask Deployment with Terraform, Ansible, Docker, and GitHub Actions

## Overview
This project demonstrates a streamline automated deployment for a Flask-based web application using AWS, Terraform, Ansible, Docker, and GitHub Actions. It has implemented Infrastructure as Code (IaC), configuration management, containerization, and CI/CD automation to ease application deployment.

## Project Architecture
- Terraform checks and governs AWS infrastructure (EC2 instances, security groups, networking).
- Ansible automates installation of software and server configuration.
- Docker containerizes the Flask application for consistent deployments and configurations.
- GitHub Actions manages CI/CD for automated testing and deployment.

## Technologies Used
- Cloud Provider: AWS EC2
- IaC Tool: Terraform
- Configuration Management: Ansible
- Containerization: Docker & Docker Compose
- CI/CD Pipeline: GitHub Actions

## Project Setup
### Prerequisites
Ensure you have the following installed:
- Terraform (https://developer.hashicorp.com/terraform/docs)
- Ansible (https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
- Docker & Docker Compose (https://docs.docker.com/get-docker/)
- AWS CLI (https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html)
- Git (https://git-scm.com/downloads)

### Step 1: Clone the Repository
git clone https://github.com/Shreyas2831/Devops_01.git cd Devops_01


### Step 2: Configure AWS Credentials
aws configure
Enter your AWS Access Key, Secret Key, Region, and Output Format.

### Step 3: Deploy AWS Infrastructure with Terraform
cd terraform-setup terraform init terraform apply -auto-approve

### Step 4: Configure EC2 Instance with Ansible
cd ansible-setup ansible-playbook -i inventory.ini setup.yml


### Step 5: Build and Run Docker Container
docker build -t flask-app . docker-compose up -d


### Step 6: CI/CD Pipeline with GitHub Actions
- Push changes to GitHub: The workflow automatically runs tests, builds and deploys the application.
- Ensure GitHub Actions has the required AWS credentials and secret keys.

## Application Usage
- Access the application: http://<EC2-Public-IP>:5000
- Check running containers: 
docker ps

- View application logs:
docker logs flask-app

- Stop the application:
docker-compose down


## Troubleshooting
- Connection Issues: Ensure AWS security groups allow inbound traffic on port 22 (SSH) and 5000 (Flask app).
- Deployment Failures: Check Terraform logs and Ansible playbook output.
- CI/CD Pipeline Errors: View GitHub Actions logs for debugging.

## Future Enhancements
- Integrate Kubernetes for container orchestration - Autohealing and Autoscaling characterstics.
- Implement Auto-Scaling for dynamic resource allocation.
- Enhance monitoring with AWS CloudWatch, Grafana and Prometheus.
