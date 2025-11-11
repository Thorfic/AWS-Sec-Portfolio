# 14-Day AWS Security Foundations Project

![AWS Security](https://img.shields.io/badge/AWS-Security_Foundations-orange?style=for-the-badge&logo=amazonaws)
![Terraform](https://img.shields.io/badge/Terraform-IaC-blueviolet?style=for-the-badge&logo=terraform)

Welcome! This repository documents a 14-day challenge to build, configure, and harden a secure AWS environment from the ground up. Each day, I completed a new lab, resulting in a daily commit to demonstrate consistent, hands-on progress.

## 🎯 Project Objective

The goal of this project is to demonstrate practical skills in core cloud security domains, including:
* **Identity & Access Management:** Implementing least-privilege principles.
* **Network Security:** Building a secure, multi-layered VPC.
* **Data Protection:** Enforcing encryption for data at rest and in transit.
* **Logging & Monitoring:** Creating an audit trail and alerts for critical events.
* **Infrastructure as Code (IaC):** Using Terraform to create repeatable, documented, and secure infrastructure.

## 🛠️ Technologies Used

* **AWS:** IAM, VPC, EC2, S3, CloudTrail, CloudWatch, KMS, SSM Session Manager
* **Infrastructure as Code:** Terraform
* **Version Control:** Git & GitHub

---

## 📓 Daily Lab Journal

This log serves as a table of contents for the project. Each day's work is linked for easy review.

| Day | Topic | Artifacts & Evidence |
| :--- | :--- | :--- |
| **01** | **Root Account Security** | [Secured root account with MFA](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_root-user.html#root-user-mfa-enable) (Commit: `README.md`) |
| **02** | **IAM User & Group** | [Documentation on admin user & group creation](./iam-setup.md) |
| **03** | **Custom IAM Policy** | [`policies/s3-readonly-policy.json`](./policies/s3-readonly-policy.json) |
| **04** | **VPC Creation (IaC)** | [`terraform/network/vpc.tf`](./terraform/network/vpc.tf) (VPC definition) |
| **05** | **Public & Private Subnets** | [`terraform/network/vpc.tf`](./terraform/network/vpc.tf) (Subnets, IGW, Route Table) |
| **06** | **Security Groups** | [`terraform/network/vpc.tf`](./terraform/network/vpc.tf) (Web server SG with SSH lockdown) |
| **07** | **Network ACLs** | [`terraform/network/vpc.tf`](./terraform/network/vpc.tf) (Private subnet NACL) |
| **08** | **S3 Log Bucket** | [`terraform/storage/s3.tf`](./terraform/storage/s3.tf) (Bucket + Public Access Block) |
| **09** | **S3 Bucket Policy** | [`policies/s3-enforce-https-policy.json`](./policies/s3-enforce-https-policy.json) |
| **10** | **CloudTrail Logging** | [`documentation/logging.md`](./documentation/logging.md) (All-region trail) |
| **11** | **KMS Encryption** | [`terraform/storage/s3.tf`](./terraform/storage/s3.tf) (KMS key + S3 default encryption) |
| **12** | **CloudWatch Alarm** | [`documentation/alarms.md`](./documentation/alarms.md) (Root login metric filter & alarm) |
| **13** | **Secure EC2 Access** | [`terraform/compute/ec2.tf`](./terraform/compute/ec2.tf) (EC2 with SSM Role, no SSH key) |
| **14** | **Cleanup & Review** | Final `README.md` update and resource destruction |

---

## ⚠️ Disclaimer

This project is a personal portfolio and learning exercise. The configurations are for demonstration and educational purposes only and are **not intended for use in a production environment** without a thorough security review.

## 🧹 Cleanup

All resources were created using Terraform and were destroyed at the end of the project to adhere to best practices and avoid costs. This was done by running `terraform destroy` in each sub-directory.
