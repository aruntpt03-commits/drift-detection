# 🚀 Terraform Drift Detection & Auto Remediation on AWS

A production-inspired Infrastructure as Code (IaC) project that provisions highly available AWS infrastructure using Terraform and automates infrastructure drift detection and remediation using GitHub Actions.

---

## 📌 Overview

This project demonstrates how to build a secure, scalable, and automated AWS infrastructure with Terraform while continuously monitoring infrastructure drift.

The solution automatically:

- Deploys AWS infrastructure using Terraform
- Uses separate backend configurations for Dev and Production
- Detects infrastructure drift using Terraform
- Automatically remediates infrastructure drift
- Generates reports and notifications
- Supports CI/CD using GitHub Actions

---

# 🏗️ Architecture

## Infrastructure Architecture

![Infrastructure Architecture](docs/images/infrastructure-architecture.png)

### Components

- Amazon VPC
- Public & Private Subnets across Multiple AZs
- Internet Gateway
- NAT Gateway
- Route Tables
- Security Groups
- Application Load Balancer
- Auto Scaling Group
- EC2 Instances
- Dockerized Django Application
- Remote Terraform Backend (S3)

---

## Drift Detection Workflow

![Workflow](docs/images/drift-workflow.png)

---

# 🚀 Features

## Infrastructure Provisioning

- Highly Available VPC
- Multi-AZ Deployment
- Public & Private Networking
- NAT Gateway for Private Instances
- Internet Gateway
- Application Load Balancer
- Auto Scaling Group
- Security Groups following least privilege
- Dockerized Django Application

---

## Terraform

- Remote State Backend (S3)
- Environment-specific backend configuration
- Separate Dev & Production environments
- Modular Infrastructure
- Infrastructure as Code
- Automatic resource dependency management

---

## GitHub Actions CI/CD

The workflow performs:

- Checkout Repository
- Determine Environment
- Configure AWS Credentials
- Terraform Init
- Terraform Validate
- Terraform Plan
- Drift Detection
- Auto Remediation (Optional)
- Apply Changes
- Generate Summary Report

---

## Drift Detection

Terraform uses:

```bash
terraform plan -detailed-exitcode
```

Exit Codes

| Exit Code | Meaning |
|------------|---------|
| 0 | No Drift |
| 1 | Terraform Error |
| 2 | Drift Detected |

When drift is detected:

```
Terraform Plan
      ↓
Drift Detected
      ↓
Auto Remediation
      ↓
Terraform Apply
      ↓
Verification
      ↓
Notification
```

---

# ☁️ AWS Services Used

- Amazon VPC
- EC2
- Auto Scaling
- Application Load Balancer
- Security Groups
- Internet Gateway
- NAT Gateway
- Elastic IP
- S3
- IAM

---

# 🛠️ Tech Stack

| Technology | Purpose |
|------------|----------|
| Terraform | Infrastructure as Code |
| AWS | Cloud Infrastructure |
| GitHub Actions | CI/CD |
| Docker | Containerization |
| Django | Sample Application |
| S3 | Terraform Backend |
| Git | Version Control |

---

# 📂 Project Structure

```
.
├── .github/
│   └── workflows/
│       └── terraform.yml
│
├── backend-dev.hcl
├── backend-prod.hcl
├── backend.tf
│
├── provider.tf
├── variables.tf
├── outputs.tf
├── versions.tf
│
├── vpc.tf
├── security-group.tf
├── alb.tf
├── autoscaling.tf
├── ec2.tf
│
├── docs/
│   └── images/
│
└── README.md
```

---

# 🌍 Environments

| Branch | Environment |
|----------|------------|
| dev | Development |
| main | Production |

Backend Configuration

```
backend-dev.hcl
backend-prod.hcl
```

---

# 🔐 Security

- Private EC2 Instances
- Public access only through ALB
- Security Groups with least privilege
- Remote Terraform State
- Versioned Terraform State
- S3 Backend Encryption
- IAM Authentication

---

# ⚙️ GitHub Actions Pipeline

```
Push / Pull Request
          │
          ▼
Checkout Repository
          │
          ▼
Determine Environment
          │
          ▼
Configure AWS
          │
          ▼
Terraform Init
          │
          ▼
Terraform Validate
          │
          ▼
Terraform Plan
          │
          ▼
Drift Detection
      │         │
      │         │
 No Drift   Drift Found
      │         │
      │         ▼
      │   Terraform Apply
      │         │
      └────────►Verification
                │
                ▼
          Summary Report
```

---

# 🚀 Deployment

Clone the repository

```bash
git clone https://github.com/<your-username>/drift-detection.git

cd drift-detection
```

Initialize Terraform

Development

```bash
terraform init \
-backend-config=backend-dev.hcl
```

Production

```bash
terraform init \
-backend-config=backend-prod.hcl
```

Plan

```bash
terraform plan
```

Apply

```bash
terraform apply
```

---

# 📈 Future Improvements

- GitHub OIDC Authentication
- Terraform Modules
- AWS CloudWatch Integration
- Slack Notifications
- Terraform Cost Estimation
- tfsec Security Scan
- Checkov Security Validation
- Multi-Region Deployment
- Amazon ECR Integration
- Blue/Green Deployment

---

# 📚 Learning Outcomes

This project helped me gain hands-on experience with:

- Terraform
- AWS Networking
- High Availability Architecture
- Auto Scaling
- Load Balancing
- Remote State Management
- Infrastructure Drift Detection
- Infrastructure Auto Remediation
- GitHub Actions
- Docker
- Infrastructure Automation
- DevOps CI/CD

---

# 🚀 Output Images
![alt text](<Screenshot 2026-07-22 121410.png>) ![alt text](<Screenshot 2026-07-22 121350.png>) ![alt text](<Screenshot 2026-07-22 121451.png>) ![alt text](<Screenshot 2026-07-22 121420.png>)


# 👨‍💻 Author

**Arun Kumar**

Cloud & DevOps Engineer

GitHub: https://github.com/aruntpt03-commits

LinkedIn: https://www.linkedin.com/in/arun-kumar-14244b366/

---