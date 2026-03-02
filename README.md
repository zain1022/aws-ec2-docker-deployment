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
### Install Docker
### Clone Repository
### Build and Run Container
### Verify Application
