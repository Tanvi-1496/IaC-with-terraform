🚀 Terraform CI/CD Pipeline with GitHub Actions
📌 Overview

This project demonstrates a complete Infrastructure as Code (IaC) workflow using Terraform integrated with a CI/CD pipeline using GitHub Actions.

It includes automated quality checks, validation, linting, and a Terraform execution plan before any changes are merged into the main branch.

🧱 Tech Stack
🟣 Terraform (Infrastructure as Code)
🟡 GitHub Actions (CI/CD)
🟢 TFLint (Linting)
🔵 Terraform CLI (fmt, validate, plan)
🐧 Ubuntu GitHub Runner
⚙️ CI/CD Pipeline Architecture

The project uses two main GitHub Actions workflows:

1️⃣ Lint & Validate Pipeline (CI Gate)

Runs on every change to ensure code quality.

Steps included:

Terraform formatting check (fmt)
Terraform initialization (init)
Terraform validation (validate)
TFLint for best practices

👉 Purpose: Ensure code is clean and error-free before merging

2️⃣ Terraform Plan Pipeline (Preview Gate)

Runs on every Pull Request.

Steps included:

Terraform init
Terraform plan
Display execution plan

👉 Purpose: Show infrastructure changes before merge

🔐 Branch Protection Rules

The main branch is protected with:

✅ Required status checks (CI must pass)
✅ Terraform plan must succeed
🔒 Manual approval required before merge

👉 This ensures safe and controlled infrastructure changes.

🚦 CI/CD Flow
Feature Branch
     ↓
Pull Request Created
     ↓
GitHub Actions Triggered
     ↓
✔ Terraform Lint (fmt + validate + tflint)
✔ Terraform Plan (preview changes)
     ↓
Manual Approval Required
     ↓
Merge to main branch
🧪 What This Project Demonstrates
Infrastructure as Code workflow using Terraform
Automated CI checks before deployment
Safe infrastructure change review process
GitHub Actions pipeline integration
Real-world DevOps gate system (4-layer protection)
🧰 Terraform Features Used
terraform fmt → Code formatting standardization
terraform validate → Syntax validation
terraform plan → Infrastructure preview
tflint → Best practice enforcement
📂 Project Structure
.
├── .github/workflows/
│   ├── lint.yml        # CI lint + validate + tflint
│   ├── plan.yml        # Terraform plan on PR
├── main.tf
├── provider.tf
├── variables.tf
├── outputs.tf
└── README.md
🛡️ Safety Model

This pipeline follows a 4-layer DevOps safety model:

🧪 Code formatting check
🧪 Syntax validation
🧪 Linting (best practices)
🧪 Execution plan preview
🧑 Manual approval gate
🎯 Learning Outcome

By building this project, you learn:

How real CI/CD pipelines work
How Terraform is validated in production workflows
How GitHub protects main branches
How infrastructure changes are safely reviewed
🚀 Future Improvements
Add terraform apply after approval
Add security scanning (tfsec)
Add multi-environment support (dev/stage/prod)
Add remote backend (S3 / Terraform Cloud)