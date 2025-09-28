# TCS iON RIO-125: Secured Docker Based Lab: Enforcing end-to-end security
A secure, cloud-based Docker lab environment implementing multi-level security for running applications in a protected manner. Developed as part of TCS iON RIO project requirements.

## 🚀 Quick Start

### Prerequisites
- AWS Account with EC2 access
- Ubuntu 24.04 instance (t2.micro recommended)
- Basic terminal/SSH knowledge

### One-Command Installation
bash
# Clone and deploy
git clone https://github.com/yourusername/secure-docker-lab.git
cd secure-docker-lab
docker-compose up -d

# Verify all services
curl http://localhost:80
curl http://localhost:5000

#Project Overview
This project implements a secure Docker-based lab environment meeting all TCS iON RIO requirements:

#Objectives Achieved
 1. Multi-level Security: Infrastructure, network, and application security

 2.Docker Containers: Isolated service deployment

 3.AWS Cloud: Scalable cloud infrastructure

 4.Security Tools: Comprehensive vulnerability assessment

 5.Three-Tier Architecture: Web, Application, Database layers

#System Architecture
AWS EC2 Ubuntu 24.04
│
├── Docker Environment
│   ├──  Nginx Web Server (Port 80)
│   ├──  MySQL 8.0 Database (Port 3306)
│   ├──  Python Flask API (Port 5000)
│   └──  Security Tools Suite
│
├── Private Network (172.20.0.0/24)
└── Controlled Port Exposure (80, 5000, 3306)

#Services Deployed
--------------------------------------------------------------
Service	          | Port	| Description               |Status
---------------------------------------------------------------
 Nginx Web Server | 80	  | Static content delivery	  |Running
 --------------------------------------------------------------
 MySQL Database	  | 3306	| Data storage & management | Running
 --------------------------------------------------------------
 Python Flask API	| 5000	| REST API application      |	Running
 --------------------------------------------------------------

 "Installation Guide"
 Step 1: AWS EC2 Setup
# Launch EC2 instance:
# - OS: Ubuntu 24.04 LTS
# - Type: t2.micro (Free Tier)
# - Storage: 8GB+ 
# - Security Groups: Open ports 22, 80, 5000, 3306

Step 2: Environment Setup
# Connect to EC2 instance
ssh -i "your-key.pem" ubuntu@your-ec2-ip

# Clone and setup
git clone https://github.com/yourusername/secure-docker-lab.git
cd secure-docker-lab

Step 3: Deploy Services
# Start all services
docker-compose up -d

# Check status
docker ps

# Expected output:
# CONTAINER ID   IMAGE                   STATUS   PORTS
# ...           nginx:alpine            Up       0.0.0.0:80->80/tcp
# ...           mysql:8.0               Up       0.0.0.0:3306->3306/tcp
# ...           secure-lab-python-app   Up       0.0.0.0:5000->5000/tcp

*Security Implementation*
Network Security
Private Docker Network: 172.20.0.0/24 subnet

Minimal Port Exposure: Only essential ports (80, 5000, 3306)

Container Isolation: Services run in separate containers

Internal DNS: Service discovery via container names

Application Security
Strong Authentication: Secure credentials for all services

Minimal Base Images: Alpine Linux variants for reduced attack surface

Regular Updates: Security patches applied

Service Hardening: Least privilege principles

Container Security
Non-root Execution: Services run with minimal privileges

Resource Limits: Container resource constraints

Read-only Filesystems: Where applicable

Security Scanning: Regular vulnerability assessment
