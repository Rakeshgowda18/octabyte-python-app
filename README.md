﻿# Trigger deployment# Octa Byte AI DevOps Assignment

## ✅ Part 1: Infrastructure Provisioning using Terraform

- Provisioned an EC2 instance on AWS using Terraform.
- Installed Docker and Docker Compose via user-data script during instance creation.
- Configured security groups:
  - Port 22 open for SSH access (restricted to my IP).
  - Port 5000 open for accessing the deployed Flask application.

### Files:
- `main.tf` – EC2 instance configuration, security group setup
- `variables.tf` – Variable definitions for instance type, AMI, region
- `outputs.tf` – Public IP output

---

## ✅ Part 2: CI/CD Pipeline using GitHub Actions

- Set up GitHub Actions to automate deployment on every push to `main` branch.
- Used `appleboy/scp-action` to securely copy files to EC2 instance.
- Used `appleboy/ssh-action` to run deployment script over SSH on EC2.
- Flask app is containerized and run via Docker Compose.

### CI/CD Features:
- Auto deployment on push to `main`
- SSH & SCP over secrets
- Dockerized Flask app

---

## 🚀 How to Access the App

- The app is served on:  
  `http://<your-ec2-public-ip>:5000/`

> Make sure port 5000 is open in the inbound rules.

---

## 🔐 Notes

- GitHub secrets are used to store private key and server details securely.
- CI/CD pipeline is defined in `.github/workflows/deploy.yml`.

---

## 📁 Project Structure

octabyte-python-app/
├── app/
│ └── app.py
├── Dockerfile
├── docker-compose.yml
├── main.tf
├── variables.tf
├── outputs.tf
├── .github/
│ └── workflows/
│ └── deploy.yml
└── README.md
