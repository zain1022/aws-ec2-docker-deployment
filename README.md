# 🚀 Cloud Deployment on AWS (EC2 + Docker + FastAPI)
## Overview:
This project demonstrates deploying a containerized FastAPI service to AWS EC2 (Free Tier) using Docker. The deployment includes Linux administration, security group configuration, container management, and structured troubleshooting.

The goal was to simulate a real-world support scenario involving cloud networking, service exposure, and log-based debugging. It is built by utulizing the same files used in k8s mini-platform to deploy the same service using AWS.
## Pre-requisites:
* Windows + Powershell (Can also be done on Mac via Terminal)
* Docker Desktop
* Git
* AWS account
## Architecture:
Internet → AWS Security Group (Port 8000) → EC2 Instance (Amazon Linux) → Docker Container → FastAPI Application
## ⚙️ Tech Stack
* AWS EC2 (t2.micro or t3.micro – Free Tier)
* Amazon Linux 2023
* Docker
* FastAPI
* Uvicorn
* SSH
* Linux CLI
## Deployment Steps:
### Launch EC2 Instance
* AMI: Amazon Linux 2023
* Instance type: t3.micro (or t2.micro)
* Public IP enabled
* Security Group:
  * SSH (22) → My IP
  * TCP 8000 → 0.0.0.0/0
### SSH Into Instance
```powershell
ssh -i mini-ec2-key.pem ec2-user@<PUBLIC_IP>
```
### Install Docker
```powershell
sudo dnf update -y
sudo dnf install docker -y
sudo systemctl start docker
sudo systemctl enable docker
sudo usermod -aG docker ec2-user
```
### Clone Repository
```powershell
git clone https://github.com/zain1022/k8s-mini-platform.git
cd k8s-mini-platform
```
### Build and Run Container
```powershell
docker build -t mini-api:1.0 .
docker run -d --name mini-api -p 8000:8000 mini-api:1.0
```
### Verify Application
