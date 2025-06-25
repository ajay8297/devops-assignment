# DevOps Intern Assignment - Nginx Reverse Proxy on AWS EC2

[![Docker Compose Ready](https://img.shields.io/badge/Docker%20Compose-Ready-blue)](https://github.com/ajay8297/devops-assignment/blob/main/docker-compose.yml)

## 🌐 EC2 Deployment
This solution is deployed on AWS EC2 with:
- Public IP: `18.141.8.212` (replace with your actual IP)
- Security Group: Ports 80 (HTTP) and 22 (SSH) open

## 🚀 Setup Instructions
```bash
# Connect to your EC2 instance
ssh -i your-key.pem ec2-user@your-ec2-ip

# Clone and run
git clone https://github.com/ajay8297/devops-assignment.git
cd devops-assignment
docker-compose up --build -d
🔗 Access Endpoints
Service 1: http://18.141.8.212/service1/ping

Service 2: http://18.141.8.212/service2/ping

🔧 Key Configuration
Nginx routes traffic to:

nginx
location /service1/ {
    proxy_pass http://service1:8001/;
    proxy_set_header Host $host;
}

location /service2/ {
    proxy_pass http://service2:8002/;
    proxy_set_header Host $host;
}
✅ Implemented Features
Deployed on AWS EC2 instance

URL path-based routing through Nginx

Request logging with timestamps (visible in demo)

Health checks for both services

Single-command deployment
