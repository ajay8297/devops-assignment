# DevOps Intern Assignment - Nginx Reverse Proxy with Docker

[![Docker Compose Ready](https://img.shields.io/badge/Docker%20Compose-Ready-blue)](https://github.com/ajay8297/devops-assignment/blob/main/docker-compose.yml)

## System Architecture
- **Service 1**: Go HTTP service (port 8001)
- **Service 2**: Python Flask service (port 8002)
- **Nginx**: Reverse proxy (port 8080)

## 🚀 Quick Start
```bash
# Clone and run with one command
git clone https://github.com/ajay8297/devops-assignment.git
cd devops-assignment
docker-compose up --build
